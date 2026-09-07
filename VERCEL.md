# Vercel-এ হোস্ট করার নিয়ম (Free plan)

GitHub repo টা Vercel-এ ইমপোর্ট করার পর নিচের সেটিং গুলো দিন।

## 1. Environment Variables (Project → Settings → Environment Variables)

এখন শুধু `NITRO_PRESET=vercel` দিলেই সাইট চলবে এবং এডিট/সেভ কাজ করবে। বাকি ভেরিয়েবলগুলো ঐচ্ছিক — না দিলে বিল্ট-ইন ডিফল্ট মান ব্যবহার হবে। দিলে **Production + Preview** দুই জায়গাতেই দিন এবং নামের বানান হুবহু মিলিয়ে দিন (ভুল বানান হলে সেটি উপেক্ষা করা হবে)।

| Name | Value |
| --- | --- |
| `NITRO_PRESET` | `vercel` |
| `SUPABASE_URL` | `https://vvxtstzygngwwqkojcgo.supabase.co` |
| `SUPABASE_PUBLISHABLE_KEY` | `sb_publishable_s1lGUWLT_aYy45W9UKqhiw_Kf4__RWW` |
| `VITE_SUPABASE_URL` | `https://vvxtstzygngwwqkojcgo.supabase.co` |
| `VITE_SUPABASE_PUBLISHABLE_KEY` | `sb_publishable_s1lGUWLT_aYy45W9UKqhiw_Kf4__RWW` |
| `CMS_SESSION_SECRET` | যেকোনো লম্বা র‍্যান্ডম স্ট্রিং (৩২+ অক্ষর) |
| `CMS_ADMIN_USER` | `deselim-admin` |
| `CMS_ADMIN_PASSWORD` | আপনার পাসওয়ার্ড |
| `CMS_DB_SECRET` | চ্যাটে দেওয়া CMS write key |

> `SUPABASE_SERVICE_ROLE_KEY` লাগবে না — এডিট/সেভ/ইমেজ সবকিছু publishable key + `CMS_DB_SECRET` দিয়ে চলে।

## 2. Build settings

- Framework Preset: **Other**
- Build Command: `npm run build`
- Output Directory: খালি রাখুন (Nitro নিজেই `.vercel/output` তৈরি করে)
- Install Command: ডিফল্ট

## 3. Deploy

Deploy শেষ হলে `https://<your-app>.vercel.app/index2.html` এ গিয়ে লগইন করলে পেন্সিল আইকন দিয়ে এডিট ও সেভ কাজ করবে, আর মেইন পেইজেও আপডেট দেখা যাবে।

## নোট

- `CMS_DB_SECRET` কারও সাথে শেয়ার করবেন না — এটাই ডাটাবেসে লেখার অনুমতি দেয়।
- আগের বাকেটে আপলোড করা পুরোনো ছবি Vercel-এ দেখা যাবে না; নতুন করে আপলোড করলে সেগুলো ডাটাবেসে সেভ হবে এবং সব জায়গায় কাজ করবে।
