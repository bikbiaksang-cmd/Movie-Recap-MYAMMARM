MOVIE RECAP MM — ANDROID APK KIT v3
===================================

ဒီ ZIP ထဲမှာ (1) AI recap backend နှင့် (2) Android APK ကို GitHub ကနေ အခမဲ့ build လုပ်နိုင်မည့် Android project ပါသည်။ ဒီနေရာမှာ APK binary ကို compile လုပ်ပြီးသားမဟုတ်ပါ။ GitHub Actions က APK ထုတ်ပေးနိုင်ရန် project ကိုပြင်ဆင်ထားသည်။

အရေးကြီးသောအချက်
- APK သည် Android app shell ဖြစ်သည်။ Video transcription/recap/voiceover ကိုလုပ်ရန် online backend server တစ်ခုလိုအပ်သည်။ APK တစ်ခုတည်းက offline အပြီးအစီးမလုပ်နိုင်ပါ။
- မြန်မာ voice-over အတွက် Edge TTS ရှိ my-MM-ThihaNeural (အမျိုးသား) နှင့် my-MM-NilarNeural (အမျိုးသမီး) ကိုခေါ်သုံးထားသည်။ Internet လိုအပ်ပြီး third-party service ရရှိနိုင်မှု/စည်းမျဉ်းပြောင်းလဲမှုအပေါ် မူတည်သည်။
- Backend မှာ FFmpeg, faster-whisper နှင့် Ollama optional model လိုအပ်သည်။ Free server တွင် RAM/time limit ကြောင့် ရုပ်ရှင်ရှည်များ မပြီးနိုင်နိုင်ပါ။
- YouTube/TikTok/RedNote links အားလုံးကို ရယူနိုင်မည်မဟုတ်ပါ။ ကိုယ်ပိုင် သို့မဟုတ် ခွင့်ပြုချက်ရှိသော video ကိုသာသုံးပါ။

A. BACKEND SETUP (Android ဖုန်းတစ်လုံးတည်းနဲ့ အခမဲ့ကြိုးစားရန်)
1. Hugging Face account ဖွင့်ပါ။
2. New Space လုပ်ရာတွင် Docker SDK ရွေးပြီး public repository ဖြစ်နိုင်ကြောင်း သတိပြုပါ။ Free compute availability/limits သည် account အလိုက်ပြောင်းနိုင်သည်။
3. backend folder ထဲက ဖိုင်များကို Space repository root ထဲ upload လုပ်ပါ။ Dockerfile ကိုသုံးပါ။
4. Space build အောင်မြင်ပြီး URL ရမှ APK ထဲသို့ ထည့်နိုင်မည်။ Free CPU server သည် Whisper ကြောင့် အလွန်နှေးနိုင်သည်။ Free hosting အာမခံမရှိပါ။

B. APK BUILD (Coding မရေးဘဲ ဖုန်းမှ)
1. GitHub account ဖွင့်ပါ။
2. New PUBLIC repository ဖန်တီးပါ (public repo standard runners အတွက် GitHub Actions free build သုံးနိုင်သည်; public source ကို လူတိုင်းမြင်နိုင်သည်)။
3. ZIP ကို ဖုန်းထဲ unzip လုပ်ပါ။ ZIP ကိုဖြည်ပြီး repository root ထဲသို့ android folder, backend folder နှင့် .github folder သုံးခုလုံးကို upload လုပ်ပါ။ (GitHub mobile web မှ folder upload မလွယ်ပါက browser Desktop site ကိုသုံးပါ။)
4. GitHub repository → Actions → Build Movie Recap MM APK → Run workflow ကိုနှိပ်ပါ။
5. Workflow အောင်မြင်လျှင် run page အောက်က Artifacts → Movie-Recap-MM-debug-apk ကို download လုပ်ပါ။ ZIP ကိုဖြည်ပြီး app-debug.apk ကို Android မှာ install လုပ်ပါ။ Unknown apps install ခွင့်ပေးရန် Android settings မေးနိုင်သည်။
6. APK ဖွင့်ပြီး Backend URL ထည့်ပါ။ Backend မရှိသေးလျှင် APK ကိုဖွင့်နိုင်သော်လည်း Recap မလုပ်နိုင်ပါ။

C. BACKEND DEPENDENCIES
- Python 3.11+, FFmpeg, requirements.txt
- Optional: Ollama model qwen2.5:3b. Without Ollama, fallback summary is extractive and quality may be weak.
- Do not expose an unauthenticated public server to strangers. Add authentication, rate limits and cleanup before public launch.

TEST STATUS
- Android project source + GitHub Actions build workflow generated.
- APK binary is NOT included yet; it must be built through GitHub Actions.
- Full cloud deployment was not performed from this package.
- Check every generated recap/subtitle for errors before publishing.
