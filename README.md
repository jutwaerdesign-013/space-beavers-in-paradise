# Space Beavers in Paradise 🦫🚀

Een kleine, rustige communicatie-app voor Kim en Selwyn.

## Hoe te gebruiken

1. Open de app-link op je telefoon (zie GitHub Pages link hieronder).
2. Kies je naam (Kim of Selwyn) - dit wordt onthouden op je telefoon.
3. Elke dag verschijnt een korte vraag. Schrijf 2 minuten, verstuur.
4. Zodra jullie **allebei** hebben ingevuld, zie je elkaars antwoord.
5. Gebruik "Dam it" als je gefrustreerd bent (adempauze).
6. Gebruik "Help, ik loop vast" voor 3 vragen die je op gang helpen.
7. Gebruik "Schrijf een compliment" om de ander te verrassen.

## Benodigde Supabase-tabel

Ga naar je Supabase project → SQL Editor → plak en voer uit:

```sql
create table entries (
  id uuid default gen_random_uuid() primary key,
  user_name text not null,
  entry_date date not null,
  entry_type text not null,
  question text,
  answer text not null,
  created_at timestamp default now()
);

alter table entries enable row level security;

create policy "Allow all for anon" on entries
  for all
  using (true)
  with check (true);
```

## Live app

Zodra GitHub Pages actief is (Settings → Pages → Branch: main → Save),
is de app bereikbaar op:

https://jutwaerdesign-013.github.io/space-beavers-in-paradise/

## Wat werkt al

- Onboarding (naam kiezen)
- Dagelijkse vraag (willekeurig uit een lijst)
- Gedeeld antwoord zichtbaar zodra beiden hebben ingevuld
- "Dam it"-knop (adempauze)
- "Help, ik loop vast"-knop (3 vragen)
- Complimenten sturen

## Wat nog kan worden toegevoegd (later)

- Inspreken i.p.v. typen
- Adaptieve vragen (korter bij weinig energie)
- Voortgangsgrafiek / woordanalyse
- Uitstel van onthulling
- Vaste tijdstippen + herinneringen
