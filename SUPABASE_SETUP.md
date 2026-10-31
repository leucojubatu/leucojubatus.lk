# Supabase setup for LEUCO JUBATUS

## 1. Rotate your secret key first
The secret key was pasted into a chat, so treat it as exposed.
Go to Supabase > Project Settings > API Keys, create a new secret key,
and revoke the old one.

## 2. Install the package (for a Node backend)
    npm install @supabase/server

On Supabase Edge Functions you can import it directly, with no install needed.

## 3. Environment variables
Copy `.env.example` to `.env` and paste in your new values.
On Edge Functions these are injected automatically.

## 4. Optional: Supabase skill for AI coding tools
    npx skills add supabase/server

## Important
- The publishable key and URL are safe in front-end code.
  The secret key is NOT. Keep it only on the server or in Edge Function secrets.
- Add `.env` to `.gitignore` so it never reaches GitHub.
- The HTML admin file runs entirely in the browser, so it cannot hold the
  secret key. Any backend calls must go through an Edge Function.
- The admin PIN is currently stored in the HTML file, where anyone who views
  the page source can read it. Move admin login to Supabase Auth before
  relying on it for security.
