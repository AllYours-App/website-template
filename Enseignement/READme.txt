<!--
═══════════════════════════════════════════════════════════════
README — SUPABASE SETUP
═══════════════════════════════════════════════════════════════

1. CRÉER UN PROJET sur https://supabase.com (Free plan)

2. TABLES — coller dans SQL Editor > New query :

create table config (
  id   bigint generated always as identity primary key,
  key  text unique not null,
  value text not null
);

create table tabs (
  id         uuid default gen_random_uuid() primary key,
  name       text not null,
  sort_order integer default 0
);

create table blocks (
  id           uuid default gen_random_uuid() primary key,
  tab_id       uuid references tabs(id) on delete cascade,
  type         text not null,        -- 'text' | 'image'
  content      text not null,        -- texte ou URL publique
  storage_path text,                 -- chemin Storage (images uniquement)
  sort_order   integer default 0
);

3. RLS (Row Level Security) — dans Authentication > Policies,
   ou coller dans SQL Editor :

alter table config enable row level security;
alter table tabs   enable row level security;
alter table blocks enable row level security;

create policy "public read-write" on config for all using (true) with check (true);
create policy "public read-write" on tabs   for all using (true) with check (true);
create policy "public read-write" on blocks for all using (true) with check (true);

4. STORAGE — dans Storage > New bucket :
   Nom : site-images
   Public bucket : OUI (cocher)

   Puis dans Policies de ce bucket :
   Allow public read  : authenticated = false → select → true
   Allow public write : authenticated = false → insert → true
   Allow public delete: authenticated = false → delete → true

   Ou via SQL :
   create policy "public" on storage.objects for all using (bucket_id = 'site-images') with check (bucket_id = 'site-images');

5. CONFIG dans le fichier HTML :
   SUPABASE_URL  = votre Project URL (Settings > API)
   SUPABASE_ANON = votre anon public key (Settings > API)

6. PREMIER LANCEMENT :
   Ouvrir le site, taper n'importe quoi → message avec les mots de passe par défaut
   visiteur : visiteur2026
   admin    : admin2026
   → Se connecter en admin et les changer immédiatement.

═══════════════════════════════════════════════════════════════
-->