[kanta_portfolio_v2.html](https://github.com/user-attachments/files/28226861/kanta_portfolio_v2.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kanta T. — Strategic Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        display: ['"DM Serif Display"', 'serif'],
                        body: ['"DM Sans"', 'sans-serif'],
                    },
                    colors: {
                        sage: {
                            50: '#f4f6ee',
                            100: '#e6ecd6',
                            200: '#ccdaad',
                            300: '#aec380',
                            400: '#90aa57',
                            500: '#738f3d',
                            600: '#5a7030',
                            700: '#455628',
                            800: '#374522',
                            900: '#2e391e',
                        },
                        ink: {
                            50: '#f8f8f7',
                            100: '#f0f0ee',
                            200: '#e0dfdb',
                            300: '#c8c6bf',
                            400: '#a8a59c',
                            500: '#8a877d',
                            600: '#6e6b61',
                            700: '#57544c',
                            800: '#3e3c36',
                            900: '#26241f',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        * { box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body { font-family: 'DM Sans', sans-serif; background: #fafaf8; color: #26241f; }

        /* ── NAV ── */
        .nav-item {
            position: relative;
            font-size: 0.72rem;
            letter-spacing: 0.08em;
            text-transform: uppercase;
            font-weight: 600;
            color: #6e6b61;
            transition: color 0.25s;
            padding-bottom: 2px;
        }
        .nav-item::after {
            content: '';
            position: absolute;
            bottom: -2px; left: 0;
            width: 0; height: 1.5px;
            background: #5a7030;
            transition: width 0.25s ease;
        }
        .nav-item:hover { color: #26241f; }
        .nav-item:hover::after { width: 100%; }

        /* ── PROFILE PHOTO ── */
        .photo-ring {
            position: relative;
            width: 260px; height: 310px;
            border-radius: 120px 120px 100px 100px;
            overflow: hidden;
            background: #e6ecd6;
            border: 3px solid #ccdaad;
            flex-shrink: 0;
        }
        .photo-ring img {
            width: 100%; height: 100%;
            object-fit: cover; object-position: top center;
            display: block;
        }
        .photo-ring .photo-placeholder {
            width: 100%; height: 100%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
            gap: 12px; color: #8a877d;
        }

        /* ── TIMELINE ── */
        .tl-line {
            position: absolute;
            left: 20px; top: 12px; bottom: 0;
            width: 1px; background: #e0dfdb;
        }
        .tl-dot {
            position: absolute;
            left: 14px; top: 10px;
            width: 13px; height: 13px;
            border-radius: 50%;
            border: 2px solid white;
            z-index: 10;
        }

        /* ── SKILL PILL ── */
        .skill-pill {
            display: inline-flex; align-items: center;
            gap: 6px; padding: 6px 14px;
            background: white; border: 1px solid #e0dfdb;
            border-radius: 100px;
            font-size: 0.75rem; font-weight: 500;
            color: #3e3c36;
            transition: border-color 0.2s, background 0.2s;
        }
        .skill-pill:hover { border-color: #90aa57; background: #f4f6ee; }

        /* ── VIDEO CARD ── */
        .vid-card { transition: transform 0.25s, box-shadow 0.25s; }
        .vid-card:hover { transform: translateY(-3px); box-shadow: 0 12px 32px rgba(0,0,0,0.1); }
        .vid-overlay { background: linear-gradient(to top, rgba(0,0,0,0.5) 0%, rgba(0,0,0,0.05) 60%); }

        /* ── SECTION LABEL ── */
        .section-label {
            font-size: 0.65rem; letter-spacing: 0.25em;
            text-transform: uppercase; font-weight: 700;
            color: #5a7030;
        }
        .section-title { font-family: 'DM Serif Display', serif; }

        /* ── FADE IN ── */
        @keyframes fadeUp { from { opacity:0; transform:translateY(18px); } to { opacity:1; transform:translateY(0); } }
        .fade-up { animation: fadeUp 0.7s ease both; }
        .fade-up-d1 { animation-delay: 0.1s; }
        .fade-up-d2 { animation-delay: 0.22s; }
        .fade-up-d3 { animation-delay: 0.34s; }

        /* ── MOBILE MENU ── */
        #mobile-menu { display: none; }
        #mobile-menu.open { display: block; }
    </style>
</head>
<body>

<!-- ═══════════════ NAV ═══════════════ -->
<nav class="fixed w-full z-50 bg-white/95 backdrop-blur border-b border-ink-100" style="top:0;">
    <div class="max-w-6xl mx-auto px-5 lg:px-10">
        <div class="flex justify-between items-center h-16">
            <!-- Logo -->
            <div style="font-family:'DM Serif Display',serif;" class="text-xl text-ink-900">
                Kanta <span class="text-sage-600 italic">T.</span>
            </div>
            <!-- Desktop Nav -->
            <div class="hidden md:flex items-center gap-8">
                <a href="#about"    class="nav-item">Profile</a>
                <a href="#experience" class="nav-item">Experience</a>
                <a href="#campaigns"  class="nav-item">Campaigns</a>
                <a href="#media"    class="nav-item">PR & Media</a>
                <a href="#skills"   class="nav-item">Skills</a>
                <a href="mailto:kanta.gubgift@gmail.com" class="ml-2 px-4 py-2 rounded-full bg-sage-600 text-white text-xs font-semibold tracking-wide hover:bg-sage-700 transition">
                    Contact
                </a>
            </div>
            <!-- Hamburger -->
            <button id="menu-btn" class="md:hidden text-ink-600" onclick="document.getElementById('mobile-menu').classList.toggle('open')">
                <i class="fas fa-bars text-lg"></i>
            </button>
        </div>
    </div>
    <!-- Mobile Menu -->
    <div id="mobile-menu" class="md:hidden border-t border-ink-100 bg-white">
        <div class="flex flex-col px-6 py-4 gap-4">
            <a href="#about"      class="nav-item" onclick="document.getElementById('mobile-menu').classList.remove('open')">Profile</a>
            <a href="#experience" class="nav-item" onclick="document.getElementById('mobile-menu').classList.remove('open')">Experience</a>
            <a href="#campaigns"  class="nav-item" onclick="document.getElementById('mobile-menu').classList.remove('open')">Campaigns</a>
            <a href="#media"      class="nav-item" onclick="document.getElementById('mobile-menu').classList.remove('open')">PR & Media</a>
            <a href="#skills"     class="nav-item" onclick="document.getElementById('mobile-menu').classList.remove('open')">Skills</a>
            <a href="mailto:kanta.gubgift@gmail.com" class="nav-item text-sage-600">Contact</a>
        </div>
    </div>
</nav>

<!-- ═══════════════ HERO / ABOUT ═══════════════ -->
<section id="about" class="pt-28 pb-20 lg:pt-36 lg:pb-28 bg-white">
    <div class="max-w-6xl mx-auto px-5 lg:px-10">
        <div class="flex flex-col lg:flex-row items-center gap-14 lg:gap-20">

            <!-- Text -->
            <div class="flex-1 order-2 lg:order-1">
                <div class="flex items-center gap-2 mb-5 fade-up">
                    <span class="w-2 h-2 rounded-full bg-sage-500 animate-pulse"></span>
                    <span class="section-label">Strategic Portfolio · Bangkok, Thailand</span>
                </div>
                <h1 class="section-title text-4xl lg:text-5xl xl:text-6xl leading-tight text-ink-900 mb-2 fade-up fade-up-d1">
                    Kanta Thanawatthanawut
                </h1>
                <h2 class="section-title italic text-2xl lg:text-3xl text-sage-600 mb-7 fade-up fade-up-d1">
                    Business Development & Operations Manager
                </h2>
                <p class="text-base text-ink-500 leading-relaxed max-w-xl mb-8 fade-up fade-up-d2">
                    10+ years driving growth across digital platforms, retail brands, and creator ecosystems. Expert in go-to-market strategy, revenue optimization, UGC platform monetization, and data-driven performance marketing.
                </p>

                <!-- Key Stats -->
                <div class="grid grid-cols-3 gap-4 mb-10 fade-up fade-up-d2">
                    <div class="bg-sage-50 rounded-2xl p-4 border border-sage-100 text-center">
                        <p class="section-title text-2xl text-sage-700 font-bold">1M+</p>
                        <p class="text-xs text-ink-400 mt-1">THB Revenue<br>Joydom</p>
                    </div>
                    <div class="bg-sage-50 rounded-2xl p-4 border border-sage-100 text-center">
                        <p class="section-title text-2xl text-sage-700 font-bold">4×</p>
                        <p class="text-xs text-ink-400 mt-1">Creator Growth<br>TikTok Program</p>
                    </div>
                    <div class="bg-sage-50 rounded-2xl p-4 border border-sage-100 text-center">
                        <p class="section-title text-2xl text-sage-700 font-bold">100%</p>
                        <p class="text-xs text-ink-400 mt-1">MAU Growth<br>aduang Q3/2019</p>
                    </div>
                </div>

                <!-- Contacts -->
                <div class="flex flex-wrap gap-4 fade-up fade-up-d3">
                    <a href="mailto:kanta.gubgift@gmail.com" class="flex items-center gap-2 text-sm font-medium text-ink-700 hover:text-sage-600 transition">
                        <div class="w-9 h-9 rounded-full bg-ink-100 flex items-center justify-center text-ink-500 text-xs">
                            <i class="fas fa-envelope"></i>
                        </div>
                        kanta.gubgift@gmail.com
                    </a>
                    <a href="https://www.linkedin.com/in/kanta-thanawatthanawut" target="_blank" class="flex items-center gap-2 text-sm font-medium text-ink-700 hover:text-sage-600 transition">
                        <div class="w-9 h-9 rounded-full bg-ink-100 flex items-center justify-center text-ink-500 text-xs">
                            <i class="fab fa-linkedin-in"></i>
                        </div>
                        kanta-thanawatthanawut
                    </a>
                    <a href="tel:0969392444" class="flex items-center gap-2 text-sm font-medium text-ink-700 hover:text-sage-600 transition">
                        <div class="w-9 h-9 rounded-full bg-ink-100 flex items-center justify-center text-ink-500 text-xs">
                            <i class="fas fa-phone"></i>
                        </div>
                        096-939-2444
                    </a>
                </div>
            </div>

            <!-- Photo Box -->
            <div class="order-1 lg:order-2 flex flex-col items-center gap-3 flex-shrink-0 fade-up">
                <!--
                    ┌─────────────────────────────────────────────┐
                    │  วิธีใส่รูปโปรไฟล์จริง:                        │
                    │  แทนที่ id="profile-img" ด้วยแท็ก <img>      │
                    │  src="URL_ของรูป.jpg"                        │
                    │  หรือ src="data:image/jpeg;base64,..."       │
                    │                                              │
                    │  ตัวอย่าง:                                   │
                    │  <img src="photo.jpg" class="photo-img"/>    │
                    └─────────────────────────────────────────────┘
                -->
                <div class="photo-ring" id="profile-photo-box">
                    <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAMBAlgDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwDqzSBh6UE0mK5jYdkUmKTvTqRIUUuKMZGKBl3R/wDj/h+td8BlR9K4LSP+P+M+9d+Puj/doBEeKMUpopAJTrI5uz9Kae9LYD/Sz9KuJMtjG+Kg/wCKPuP94fzFebWw/wBFj/3RXpnxTH/FHXH1H8xXm1qP9Fj/AN0VqkZk0I5Bq7HVWJeKtRkcUCLMBxVoNkA1VjHFWEHy1Mi0yVWqZGycVXUcVIoPasy0WM9qaaQZpwBNIYxj2pFHtTWyHPPenqRgCgBwXmnUA0E00AUUA0YpgFKKTFKKAFzRSUUAKKcKaKd3oAWlA5pBTl60AOUU8CkWngdaAG09OtNxT1HSgLE6nilJ5piUueapENWH5FRSEFelOPWozVCIjSUvc0YpgFKBxSAc04DikVcBQRSikJpiW5PEP3Y+tKeKI+EApDzUMrcM54pAcUCkoGO6mhuTSCloSATFKo5opRwadgEI5o9qX3pOtSwF780tGORRinoAU4U0CnCpYDwaXNNFFSA7NIaSlJoATPNIxozzSE0x2CmmlzSE1SEApGGaUGkqhMQiilzRS0IOHyKKZT1xg1mjQO4p4poHJ4p+DQMKB0zRg0ueMUE3LujH/TU+orvzwB9K8/0ji7jI65FegkAhee1FgIiKWnDFJ360rDGkUafk3h+lONGnf8fZ+lXEmWxj/FTjwdcf7w/mK84tBm2j/wB0V6R8UufCVx9R/MV5zaDFqmePlFbIgswj5anQVFD93HapVpMCzEOKsJwoqCH7lT+lTIaH09Saapp681Fimx26nbjtpgHNOxlaLDQ0nJzSr2pCtKgHQ0WAkFBzSgcUYoGIop1O20mKAEopcUuKAG0oFLg0oFADRTu9IacKAAU5KQDPSnqMGgB6jinjvSDpSjvSYCU9e2aavWnNVJA2PBFGeaYKcnWnYgc1RE1KRkcVE49qpCIx1pc0g6mk2mmMePWn8Ypq/dFLQAdqa3WnUhoGiwpBXNIetOjRvKGBmkIweeKlghAKCOM04UvakVYYopSKVaWi4rjcH0oCnvT6PwouMaw4pBmnnkUgFIAop2KTFIGIBTgKVRS4560gEoopDSADQe1FB7UDGmg9KO9KelUgG000ppOc8VVrksVTSkGlVadTaJIx1ooPWilYLnCU5abSis0WSqeOtOqNOtPFMBaO9FLxiglouaT/AMfgrv15iT/drz7Sf+P0V6DFzEh9hQERu2kwc080UixjHApNO5u3H+zSMTuIp+ljF2/+7TjuS9jI+J//ACKF1+H8xXnUP+oX/dX+Vei/FTjwddH6D9RXnMP+oX/dX+VbIyLkAJiAUVIuQQMUlp92rCquQcUASR8Cpl6D6VEtS1MirD16U+IHmmJU8Q4qQDbTwKOKUdaRaExzTwFxSUCgY4ClxSUtAC496MUlOFACYopacoz0NAEdFSFaYetADe9OFN707tQA9e9PHSo0BGKeOlADxThUYHvTxQAq9acaBThTsJjR0py9aD0pVqkSOHK1HLUozjpUcgwM07CIT1paQnNKKYxR0paQdKdigBKRqdikK0AWY2PljBI5o+tMRsKFx0p46VmUgpD1paKRSAUopaYTVJkJDs0E02kY8UxN6jxSjrUeeKchqWUiTHvRj3pKKkYqAZOaGHNANFIBKQ0Gm0DHUHtRQe1AxtKelHU0EcdapEtjRzRjmhV5608CqTMx2OKaaWkbrQ2Mj7mikooA4agUtFRYscnWn1GvWpBQAopSMCm0vOKZNy3pXF4td/H/AKpfoK4DShm8Qd816Cg4H0FJlAKXigik6ck4FILEb43GnaX/AMfT/wC7TNyseCDT9M/4+T9Ka3FIx/inz4PuV+n8xXnkI/0dP90fyr0P4og/8Ircf8B/mK8+hH+jR/7ordGTLdqQU4qytVbXAwPWrQpAiVOlTCq6Zwc1Yj+5mpZQje1WIM7Bmq7VahwEGRUDSHClHWgkUHAFBVhaWkB706gdgoooOaB2D8aWo+c08ZxSEOpyGmUoOKYh7N7Uw9aCeaTIoGA609RSKvPFOUHNADu1KKQ8LmgHigB2aUGkFKvWrSAcKcKQCnAGmJgeBTkppFPQc0EkijikuMeUBSjio7g5Xb3pgVyKctNPSnJ1oAeBRinDpRQA3FBpaMZoAVetSjpUajFSDpUWGgoFITSihoExxphpw5zQalbhcbTW5FPpMDNai3EHQU5aQ9actRIpDh0opwpRyKhjI6M+9KRTcGkMUmm0UUBYcKDQKWgQ0daev0ppp424p3ExCR6UZFI2O1MqkxWHVG5PrT801hzSCw0UU4DiincLHDGlwKb3p9QUgwKKKUCmhiUuaMUYoZBe0f8A4/EY+or0FSAAc9hXn+kj/SEP+1XeE8L9BQUSEg9DQcHjiqk7sG46U1XY9TUtgWCEBwABTtLwbxh7VCM1PpYxeuf9mnEmRkfFMf8AFLS46lh/MV59CD5KjsAMflXoXxQP/FNSD/aH8xXBRgCFT7D+VbRM2LCSJFFW81Uj+/n0qyDTCxKn3asx/wCrFVIzxVqM/IPpUsoUjmrKHCgd6gXnBqapGO60pHFNU804nikUnoOSn4qNSafk0AmLiiil20ihtFLilC5NCFcQUtOCe9PC8UwITSCpGHNBHGe1AEgFOCj0p1unmLnpUqxEdSDQBAyjGKbgDpVsxA9aaYV9/wA6AIBTlHNTeUo6ZpAmDzVolsbjilA44p2M0hGBTuJsUCpAMdajXNWsfIfpUXAi71BP98n1qYk1G4BFWmBBTlpD1pwFMBy9KU9KTpSg5ouAhzRGfnANDGlReQam4EhBpaUGg4pgNPWig9aKGAoNFAopWsAUUGk5qeYaQjU5OlN705eBQOzuSA07HGaaKUnFSymIabSmmnrQCA0hooosIUUtJRmiwDhS5xTQaTPNMSFJ96bRRQMKG7UUMaAEopDRQBw+KdSUZpCuLTsYFNpc0EXYtFJmjNMpGhpP/Hwg/wBqu5Y9B7Vwuin/AE1M+oruSMv+AqblEUvLYpq06UfvDSCkBIOKsaaf9Mf6VXHNWNOH+lSfSqijOTMf4nf8i4Rjq4B/OuDQ/uwPYV3nxL/5F4f9dBXBrwg+grVELYcpxkeoxU6jAH0quGyAKsIeg9qYx8fSrUf3BVaOrMY+QVLKTJUHSpsVGg6VLUDExS0UGgWo9ScU4NTM8YxQKC0Sg04cnpUYp6HmgZJigDmgUooAUDmg0d6U0ARSU5BmMZpJB8uKardjQBatmCAgntVgMh6Gs8uq/eqP7fCG2jeSPRapIV0aZfHWgMGGRWLc6nbIo3z7GzjaRTxd2oTKX8a8clnxTsJM1c0VlLqFmSBDqlu7DqA4NMl1uGInzZUQDuWFOwM1ycUm7JxWRHrumykKt7CWP+2Ktm4QgNDLG4PQhqTQi+vap2OF/CsyO9iX/WkqRUv261bgXCjPak0BYNIopkUiuCVOR61InSqSAryDa+BSrRN/rKFpgO7Uqik7UBsUmAY5qQHAqPdS1OwEgORTj0psY+WiRtpxUpiDvS96aGzS5rS4x4FLimA0uRSeo0DUlHWjGO1Q0MTvSgcUnenD0oGKKU0g4oJpMbCkPWjNIaYmwopM0tABRQaTNADhSdzQDSA/NRYBaKWiiwCU0mn1HTSACaKDRTsBxBoHag0orNEC0UUVQBRS4NGDQNbl7Rv+P1K7tRkA+wrhNG/4/V+oruicYHtUMoZP9+mCnPzzzTQaAJFqxp5/0mQ+1VlNWdPObqT6CqiQ0Y3xLP8AxT4/66rXC4+QV3PxL/5ACD1lWuI/gFakbDV61YTt9KrL1qynb6UwHocfnVtBgCqsRzx71aU8DNTIaJ06VJUcfSpBUFCGgdaXFIeDQBIBmjGKRAcdeKcRQUgBp61HnFOz70DH7uMUhcjoabmjrQBKjbvrUmMVChwN7EKo7ms7VNatLNGzLmQDKqBnJosK5p3BKru4HasnVNTWzwWuYIzgnLHNeYeLPiOsLsjXQLZwUj/gryrxD42v9SmcRu8UZJGN2atRIPcde+Jmnacj7b6K6lGQFVeAa4G5+L2oC43RMm3qQVryW4uZbg7nbDd8VCu7PLE1aQHqk/xd1yXcixW+TnBVOn51zd34r1q8kZprtwrdUHArk43IYEE5HerCyOeMkmqSJeh0n9uzrEgDBGBzuDHJqGbWr+Zdv258d/mNY3lSEBmH601vl4ptBc2E1S9jO77Xkgcc1raT461SwmRpXWQKMDFcW+GPzNgVE/lAEBmzSsM9h034w3EbYuoMjOQc1u23xn0ORQt5EyMeAwTgV8+lsjg80m4gEEHJpNCufV2keONDu4RJbapDEW5+/XV6TrQuAuLiOXcPlIP3veviZVlU7o2KH2OK39A8W67o8sZtr+UKv8LHIpWKPs12Z23jDL7U+Nga8U8EfGG2uUS31mLypxwsoPDfWvTdI8T6TqIXybyHee28UWA6Bqbmo1mRhuDAj+dOVwe1IY7NOBNMzTkzmkwJk6UjtxSITikcms7FWFBp69KhBqRTTQWsPoHNFJkCqAXkdaCaaWpMipYw3c0oPOaTj0pwx6U0A4UE0mfekyD3NDQC55oJ4pvelPSpAM0oNNpQRQAE0ZoakqwAmhetNY80AnNIB5pKCaTNAC0UmaXNAAaKQmincDiqSlpDUJCY6ijIo4oIHCigUUMpbl3SeLtMdciu5P8ASuG0j/j9T6j+ddyfvn6VNyhhppxTjTT1pAKCBVrTuLmQ+oqsozVmzGJj7iqhuSzF+JhH9hR/9dhXEn/Viuz+JhH9hxf9dhXGc+WK2M2MT71WFOKrqfmqdefagnUlhBzVzHIx6VVgB4q2o6fSpkUiWPk49qlUGoo8hvwqYUkihuQKQnNKwpo4pMZPEOBT3Axx1psRBXinMOtIpEZFJTjTaBgM012CjJyfYU12O4/3P71YfizxJaaFp73EzBmwQq45/CgTdiDXtdhsEmn1FilvH91QfvGvFfG3xEl1GaSKzTylwV3jqB6ZrD8a+Mb/AFueVJZWKE5CDgCuQYlhzz61tFGbYTzyyytIzZLHJpm1jzTljct9049amjTBG48VVhXKgIzUsaM7AKMk1uWNjZyN80hIxx8vU1ei0hUK3SoRGv8ArM9hSbKOVKsrFSCDViEBAGbqO1bi6cJ5rmdUD28Yxu6bc9Kx5Y/JJD/hmhMTQ9713TEat+IquWZskmnGVVPRmGOi0SCaWAskYC+tWIquxY89KdDFGf8AWMfwp6wP3xT1hbHamwYNFAEO1W+ppqKoYFVGav20J2csPzqSSKJEBcLn2pCKTO2ceWmfekliXjzIvLJ9ORU8qxMQRIQPftSYC/dl3e2KaRRXiBj5AP1qaO7lhYPHI6EHIKsRStvwQVwvrioHGR2NJofQ7Pwt8Tdf0SZFNwbmDPzJLz+te4eBPiVoviQLCG+z3eOYXPX6V8sGJiOOaIZJrSdZYGaKRTkMpwc1mwR9xLIjoHToakQ89a8G+EnxYfzU0zxHLuThY58fzr3O3kSWGOaGRZY5BlWXkGoYy0p6801jzTN2KccEA0rFJjlxTwRj3qIHBpSeaEgbJlNI1Rg4p3amwQDNI3ApwprUgAHinA1HmlBoGSc0nPrSA0ZouIfSimE09QaBiGhaD1pRikmAdQabSlsDimrzTuIQ9aAQTS4BpoGGoGOoopaAEopcUlIAPSilxxRTFc4kGg0wCnVKQrhnAoB5oA5oA5piJFJPalpAOlO7UMa3Lmlf8fSEf3h/Ou6xnnuQK4fTP+PpP94fzru1Hyj6VmyiEjmm45qZ1phFACKORmrNr/rvwquBU9mf37fSqjuSzB+Jn/IDi/67D+dccfuCux+Jn/IDi/67CuO/5ZitjJkKfeqxEMtVYfeqzD94UAi1EOKtR/eFVovu1Zi+8KmRRMeBkc1ItMHWnipQ0BxUbcU9jUbc0MZNAxA6VMzZWq8fAFSg0ikNxmmn74Ud/wBKbNKMYZtijkmuc8SeIWtbdkspUUH5XlLYIFNK4Nk3ijxDZ6LayTTNlkUkJnv6mvmvxx4v1DxFqMsksj+Ru+VVHQVtfEjxNFeynS7CR3jT/XTOctIf6CuFJ2j5mAUdK0USG7kWxiMnOe+aejLGnQMScUB3b7hyvrUUjqDgDitEiL9BZJn3YzxTCxPU0m7jNA5oYzTtZ28pQCAM4GK2f7W8rT3so2D7uGPWuWR2XjNW9HlUapAZT8u75s+lZvcpHqWi6cILNJfLR0njG8Hop7GsDXtPsoC7SZmkyfmIAA9sV1mgXUJtZrVW3R3ABjZj9z2/OuW8Q2M6SyQTqwmU/PgcYPSgpo4m6KK7LGuOaijZ87QxA9Kmvo/InK7ajj5Oa0TJasWUti3PAP8AvU+OPHDg4Bxwc1DlwPkAJ96duYcuMf7pqiR86ptARsE+q80nl56tninI+RypPoTTGwrcsQfSgQGFSOeabIgHIVvqp6UpYlgQxFLJK4YjdjHWmURrJcKcsXA98YqRXVxuk2Z9QKjMgZTn5qjPC8Yx+tSy0WGV8HaqkeoqG5BdAEPfnIojcqeC30zTpX3ADGMVDCxWVDG4YseOor2X4F/ED7HdDQNXuCtu/wDqHY52k9BmvH2I70qMUdXQlWUghh1FSI+2ScgEHNPU8V538GfGCeIvDyW1zIDf2q7ZOfvD1r0HdQNEmfpSjmos1Kh6UCHd6cMmgU5cZqHuCFAprU5jimE80rlkbDnqaVRzjmlY80qtTAUCkxTtwprGhIAycge9WO1VB94fWrJptANPWjtQad2qQGY96RRS0oHNMAGPek70/FN70AJSinHpSUAFIPpS00GgBxPFFNLelFBLRxIFLtNIvWn0riG7aRRzT6AOaQDgKfj5aYKf/DSY0XNM/wCPpPrXcjoPpXDaX/x9J9a7peg+gpWKCkYcUtNY0AA61Na8TMfaokqW2/4+H57CqgtSWYHxK/5Acf8A12FcZn5BXZ/EnnQ4wOolBNcYR8grZIzYiD5qnj4aoEzuqeIfNSYiwnBxVqP7wqtHVhDyKViiYfeFTVXU/MKsd6Q0IaY3WnP0NRrUsZIlEsixxF2OABmgZHIGa5P4geIEsLM2drIj3LjkHonufahIaZW8XeKLKwjVZJN0j52Qg4J9z6CvCPHPjDUNT1KWK3kVI+hCHt6VV8Yas8tzMLe6kl3N885+8x9vaucgOzMhHFaqJLZMhO4u+Sx7mmyhpHAOCnenZ8wZHSlKMq5IwtaJE3GOVRSEBC+lV/mbJbFPJL5I6U18BadhWuNJpVNNIpyipZQ4g0sT7JVbOCDUe6msMkUmho9E0nVkj021UMoMW7J9z0rotaNzq2jxasFiyFEUyg7SwHevNdDYyu8LDgIWUe9ejeDLyK7hOnTCIK8ZHI/iFZSLucJq0K72CxOHA4OcjFZHCnOcnvivU9X8P2n2ua3MQV/K3gq/TNctqPhgRwNIsnlup+VT/FTTEzm1ByCQeP1p7Oo5Mbj8KSZLm3O1kYkHrQs7H77Mpx0rWLIHB4iMggn0xSGBZH3CfaO4x/Wm+amcAP7/AC0K8RIBjwM9aoRKkUPKo2cd80LCBnc30FRSGDHylfwqONgGIUkUDHOgGRgbj3ApgQbMM53+9TCWUEFfmGec09pUP341NJloriMDB3c+vpTXIByTkVZQxknCgKarTx5G4MMelIe5HIyA/KTikYttyvNVyrAmnByvepEdj8MPEJ0DxZa3e7ZGzBJh0ypr6ttp47iBJomDI6hgR6GviKNj5itk8dDX058BvEg1rwsLGRw1xZ/Kc9dtJjPRqlj6VGoyetTKPSkSSgZFKBSLnApw5rNghmCaaRipcYNRvnNNIq4w0gNIc0gqhj80lJSGmA9fvCplPFRIOakXpUvUBTQDRSUgCjvS0lAC0g60p6UtABSE0ZxSUAJmmtQTzTT0oEOXk0U1TzRRYdzjx61IKhGamTlQfWlYgXFJ3paXFIAAFOx8tJThQNblvSx/pUf+8K7gkg/hXEaaP9KQ+hFdsex9qVigJNNNBpDSuA5CaltyftT/AEqFamthm7b/AHauImYXxE50ZP8ArqK41v8AViu0+Io/4k0f/XUVxjD5BWqZkxkf3qtxAcYPNVkGGFWIfvUmInUYFTLUINSKTipZRKp+YVYB4zVRTk1bXoBUjQr/AHTUa4FPPQ1nX12qMUB2hQWZ+yimkMj8Ua3Fo+ltMrBp3+WNc98d/avnb4geJRMZLO0laSSQ5uZyfvH0HtW98WfFbRTvbwsXuH+6u7/Vr6/WvKZCWJZj8zcmtFETEZg7ZbmlXBUgVGB0qdEAXjqa0WgrD7dMx8kKBUMkhdzGD8o71LIx8sQjG7vimHCgBcdKYhqr29ajcE+1TAZ56VNHAJCAcgmk3YaTKWwnoKARlhnkVpGzVI3bccAcY9azNp3scdai5TiRZ96cKWOPnDcCnBcnjoOtNiSLVhPLBcReUPvfKfcV2NhcxWlzbTJvOSGOP1rjoEwFk7L92ur0GES2+eS8ZDDPTHes5M1UTuvEk0d5AkseDIANwjbkr6VlX9zBNbG1WYK38KSrg/8AfVSW7+ZfLExzGEyCOzVY1W0W+NskcYlLDOcY2+hrPmsUoXOK1q0liG0xYdeQd27IrLa3BUOfyru5NPspkulmLB4MhSGx0rEGkSSRpyxLkjIHFaKaE4HNSRkKduagPmKckfpW3eaXdQPhsYzis+7ieLJP51oppmcolN8PyUwfZaYqlR0PHap0lkwcKxH0przsR0Bqrk2EjkKrwQB6Ujsrg5b8BUZwewo2IfakUhI3dDkPwOxFTSSF48Dai9xULLzgGoZFIzk4z1I70mxjrhCMFQfrUDdcGrMMvAjlOV9fSkcRBiAdwPSkIhRSRkc12/wW8RNoHjOAyE/Z7g+W4zxzXFqNvC1ZswRKkyHa8bBvyNIdz7a4yCo4IBH409TzzWF4M1Ean4X0+93DLQLu59OP6VtKwPIqRFqIgrT+nSoYW+U1KKRPUU1GQM1IaaetIe5Ay9TTMYqweSRUFUikHFAxSUo60xjwRUiniohTgfekA/vThUampBUsANIadSEUANNAJoNAoATkmlIpucGnbqBCYprdqeTTGppDGCiiiqA48dMVKuQAKiTrU4rNkC4FFN5pcGkA7ilFNANOFA1uXdN/4+F+tdoeg+lcXpv/AB8L9a7Q9B9KlsYdqQilFIaQwUVLZn/TCD6VGKktP+P5v92tIkPcyPiKP+JIp9JB/OuJJ+UV2/xF/wCQGP8AfX+dcQfuitUQwHJqaEYb8KhQfNViAZOaBEyinZwOlIBgUE1Nih8Z+YVbVqpCnmQ8IvVqLDRJdT4VkXkng1wPxP8AEUWh6Y6r8rMnCg8lveu31B4bOwllmYKEXczntXzH8RvER1/XJpY2PkRMVT/a96Yzmrm6nvr6W+uXJZ2Oc8/QVXdt77qUnChfQ5po+9mtFoNC8gZqSNsIxxzTVG44HX0pHO1tp7daZLHQjLmTqAMU9VyKkjxGnI4x0pYPmY9qQ1ERF5AIresNMnlkjUKAp5NU9ItTPfxhx8gOT713Vhbxtu34KqQQMc8Vz1KiTsdtGldXOS8VQyWtnHEkapG7cHua5ryzjNdT43na41F2UFYogFRT61z1sPMldPQ4FXFmVZLm0Kc/ygZ65qxaQjyi5PLdBU9xDvukDrjauSfWnWyGVhEvy5Oc+lWyIwL2nwxraSB4wWxu+la+jxRozoxYMy9M9jVvw1pyOkskoDjysYqCaCSLUFeDI6cn0zWMmbxg7G74UdJXu45xgxphT3z2/lW34TO7UfOkw6rkFfbsR+NcxBL9m1+WdCDFsywBzu45rpPC0kUlr9vhyPKBUg9KzZoolWe3jurqaJ/lElwTuHXaKNP064QTS2+THGSGRh1+lSQHzbyWZSBDsLD6mussraMWaAnBmCvjHNLmQcpxmpm0uFgd7cxSEbZFPUVyniKzS0lPkqZI8n5T2r0jxLYxy3W5RsVkwWH97sa4TW4poXkiuM7ichj3FawZlOByM23zCBn6ZpjREoWXY+O3erTqJCWUDBPPrVG4RomJiJHrg81ujmYjpCwUplD3qJoynzA7hUiSF+h57g0pVJBtZsYPPaqEVywyeaZJyAKllgjXlCSaru6jgk59MVLQCNwaTco+8fwppahW3sA4B9DQA9WDHgGp4T6Gq4Cg9aliK78HnNLQD6P+AWsR3nhI6ezAzWzlRk84r06Lpivln4V60uieK4DI5WCYhCM988V9P2syPGro25TzmpbHYvx9MVKWxVVJARxUgbNKwmiff700tmos0uaAQpbBqM8U8DJFJJx2plDDSc0HmjtUtgOBozTefSjNFwJVbAp6tmoSeDTkPNFgJweKXrTQacCKQDSKQU80gxmgVxh60g609hTKBNik800nNITRmqQxKKTNFFrjOQU1KvSol61KnSoIH0opBSikA4dKTFKKMHNOw1uXdMXNwv1rtCOB9K43Sf8Aj4A967UDKr9KixRGM+lIakUU0jFADRUtp/x/N/u1GOtS2HN+/wDu1cTORk/EP/kB5/21/nXDvwxFd18Q/wDkA/8AbQfzrhpvvZ9QK0WpmCdanjODUCdakAORimBchPBzUfelX2pD1pMocvPFPIx9fWotwXn0pdQuks9Pku5CAscZY59qCkebftA+Kjp2jJo1rIPtNwBuweQvpXgjthcDr3rY8Z6y/iDxVe6hIdyB9kfPAFYylSSW9KpIaIj606FHc5CkgdaQDNOjlIYKBxVlEiDA3r97saYo3Sksc7Tk1IuOeeAOKS1iBcgHryTSuFiaY8quOWGavPHtsxwAzc8DkVVtgGfcwBI+UVduQcjntU3N6dPubvg22WWV5CV+QgDd0B9a7qKOGC3FxsBbnHH5muZ+H9klxbHIBLNkg966zXVhS18qIbVSM5x3rgqu8z0qKtE8r8SXDXNzNPGMoXqnpkf+nou0ZY5rQMDS3aoBlDliKZDGserDbwAOK6INHnzh7zEFuJpruU8LCn603w3814hCZz7dBU8LbbS9OMB+M/U0tjbtYalaKEyrgH8sGlOVthxWp2/hW2aRr2NgAdnp05rCvIpI71rdSSxRwufrXYeEgtzqF4y/KrqM49wTWDqSBdegbbwc849qxu2zrcbRMuAmAJIgDNLF5bcdM9a2dBkaHTLqGI4YqSc8DpWLl47KcMTlXx9Oa1oYpH08mBhHIwwxHpiqvoTYu6IRLCoYNtRhuNdog2zQnH7t2Cg/3QRxXIaYvkaVPE+PMBAyO6n/AOvXdWUaXehHOdwUBSOx9f0qB2MnxSssOiyMoBSOcHI6jOBiuc8RacmpLG1uC0qw79vtXXoY9R0e9sZ1aPaRl25wR3rjoZ7jT7ryLmQb1yA3qvatYNXMprQ8vv8AdaXbEN0PK+lMlljuCHUDp3rW8W2u+7uJCCCTu5Haubhfy/l7V1RaOGSsSyoQ2FXB/vDoaYIjIC2cOOx71LFIQdrHKfypJYA7iSMgP2z3qySuVYcYNRyjsykZq5LHuUYGxuhGaryDYDu4JpMCvtAGBmmjg08jPSmOrA8/zpAhcjFOXgg+lRrUg61IG1pIEt1bk5yJFI/OvrLSEMFlbsvKvEpI9Divj+xu3gkVlwcEEZr6O8CeOLDUrKxsZrndMECtuOADUW1KPRYDuTcox7VMhqlC5SRSDkSdcdKsqx9aoVyalHSmk9KUGpuMkU45qN+pNKelIaAG0UmaM0gFFLRRxSAXGRTlHekBoUnFU9gJVpwqMdetOBHrSsSxWNMzzSmkqrCFzmg9KQdaWmA3FJSmm0mFxKKTvRU3GmcoFNSKKBThUiDBpaWigBRSnrSDpS9qoa3L2jD/AEwV2nRVz6VxuikfbF967KTov0qWK4Aimk0rUgGT1pWKE71JYH/iZMvYpUZHNO08/wDE1b/cqokMo/ERc6AT6OufzrhJcYH0Fd78Qx/xT0n+8P5iuClH3foK1IaETqKlUdKiB5qUE8UATrQetPUcUuBikykRH5fmxnHNedfHnxFJpnhlbG3YrLctlsddvpXol06xQNIeijJr5l+KGuvrvimWUsTDE2xF7cU0NI5SAhc5GARn8aQAkbvzpufmNTKCISSuATVosTA20igM2cUpxt60Q8Bj7UdAH4/dkr1PWrFoB5TtjntUIG2P6Yq0D5cXAwNvFZNlpBZgkkDrnitKW3aOJJCd5Y4Aqrp0LG4jB4BIrftIhLdpAMYjBY59KiTsrnVTWp1/g6zjsrSPDAEjcefUVoT7Wsr2dwWQREL7mq2gRPNLFEoJEqjt0ArU1vaqizVcDYRgDvXA5XmelGNonm0sQgvbYLkhocsT6mq2pKIr9XXjMWTVq73yvG/G2OTYT6YqHW41F9aPn74IArrRxSgPEAaysk2E+ZgsB35rT8TxGyjsr6JQXQ/d9BTtIiW48gnjyWwfoa1vE1pvtShAx5Zwfepe5cYKxqfDd0ne5lULiUBgM81T8R2ogupZF58l8/QH/wCvR8KnaAQK+Mksh9cCr3jqNfJujFkb2x9axvZm0djjdQjZP3AUt58gI9812Pg2BGjMcsWWCmPn6da5mytml1OzEpJUDP5V33ha0RZpNz4O0umT1NNslxOdswsNzdQSoXYAgHPTFdXoLsdEuCGI2rtA9/WuN1hpYfEE7/wuTnHvXTaVcxnS5ApIVguOe9FxNEmrxPbQxyR5y6YYZ64qvrNra6lZW8pjG6RdrgdQ3rW1q9uW02CJhhk5B71iWziTTC6AiWNiHFVEzcbnn3iOBwrw3IDCD5FcfxexridStfs8gCghWGQc9q9M11FZpvNTG8ZX6+4rz/VbWbdgHIU8fSuik7nFXVmZEbkNyeKe4eNw28lW6Ux1IyKVWyvlsflrpRzkm/BBJp0wjdOevYioCCvU5FN3MhJ6igZDMjIcnp6+tMzVx5EdAuOD1qtJEVY7ckUhDAcc05WycU0ZzzSllAwVP4UmBKpAPNW7S6mtTuidwueMNgg1QXc33QfxqzbEhSr0hn0Z8Dtdu9V0OVL12keIgKeuBXpaGvIf2eIUNjdzKxBBCkA9q9bDKO9IVicP61IrVWzT1b1NTYosE8UxzSbhjrUbtzRuA/NFQhqkU0mrASClzTKdSExd1KGphNKKYyVSKcKjTpUi1SE0LSYpwoPSmTYbS0GgUANPSmZ5pzUypYDSTmig+1FK4rHNCnAUgFPFSMKKWgDJoAF7U8jilUdKdincCxovF9F9a7dhwv0ritK+W9iPvXbngL9KQEJFOUU40L1qrANIwDUenHGqn3Wp2Awah0//AJCn/AaErCK/xC58OyY/vD+Yrgpf4foK73xvl9Bm9mA/lXBvyAfYVoiGNQZNTBeRUcY+aps4oAlU0o5bAqIGlLFfmHaixRjeOrz7F4W1G73FRFERkdyeK+Vb1XE+XJJPzH61778eL/yfDlvYq2PtUvzDPUCvn+5OLhlzkA00VEjwKuToqWKneNxP3aqDGRVq5/1aKRggZplFTPqMVNb8oRjqarnLZ9TVi1GEx3oAtMp+zhj/AHxU10MR7c9hVZ5f9EA28+aBU0+SxFZG9NXZfgynlMK3fDsXnarIMZJgwM+tZ2nQCSOLd2rc8GRCTUJ5s/dixisKrsjupQ947jwYio8rsSRGFQe1XJLdrrVpH6xjOOO9VfAsZe2uHdgO9dNZRhZ1DuFMkPHFcHU9BrQ8n8SWQs7K/Cg71uQQvpzWV4khKWtldKc5cg+3FdZ44tz/AGhewkjcSHxjtXPavELrwmjo3zQOd6/ga6Ys5JxL/g6ETzsuTsZQfxFbGpW8k0MqmT5owDz3FZfgBlYQEnb8rYz3rotZiKzjBCbl6H6UN2ZUY6HP+D7lkmYKAHjnDL/uniuw1m2N2YYdow+QW/DOa47Qke31SaEBfl3A56HuK7y2nF+0U8MRKoPm9+MVLGkcLCjwaxFDvB25AI9+K7W1j2vbXGSEXnPr2xXLa1YOLpXgG3yWY57kfSu70i3F74ZjjQgTrwpP86iTLSOc8R2im4eQgATcqfT2qn4WmC3BtJycB8Vr3tsZ7AzOpMkPDD096xzCYr13V1JOxuOtC1JnHQ7i5kL2KySfwtg4+tc/O72V6bpYx5b/AOsQn7w9RVyG7Mtgk2/5BlZMdjWJrE8DW5eGQvskzz6YrRHOzN8UQliLu2IZmGQT0I9K4TV3VssF2uOGFdPdXLw20tuSwRvnhLdBntXL3+17iQfx7cEetdNA48QtTm7kEgleD3quHbowq7dII3bHIYYqoGAOCM11I5rDS3WlDrt56mkcjnAx7VGcZyaoCQKO7bD2pwaeLJ2hl9e1RB+MMMiiOdlPy9PQ0mSTZjl6jBpvkJ/fFOE0bIRsCnPOOKGFuYyVLqw9TxU2Ab5cQOGfn61agKgKgkBX0xVTYSmcbh61JHGwYMBSHc96/Z/kSPR7+VVOS4+WvWFIdEbPUV8+fB/xGNM1FbeciNJTgFh396+gYJ4JYklVgQ4zwakCUDjrSr1poI6j8KcuM9aLjH9qY3elbpSdqG7ANFSqcVEKfmluBLkUEiosmkJNFhE4xSio1PNSA0mMepqQYqHPSn7sUwHM2OlIrknGKYxzSRffpktE1KKSjevrzTENaon6092prVMgGp1opwoqQOcxxSikGacnWgBcH0pVBzT8Ug60gFApTTgKQ0AWdN5uk/3q7hhwv0rh9OH+lIR6iu4zwM+lNAMpFNPIpMCqARqj0/jVOf7tSmq9nn+03H+xxQJkPjQ58O3JHZh/OuDQExg+tdx4wyvhe5z1yP51xIOEQD0H8q0SJsCDBp5NMU0hPJxQOxIM0MX+4MZJpqNUkfDhhjPvUsDxr45XaSeK7KyckR28Jc5HevG5W33EjjoW4r0X40TyN4wvGkO5ljCr7CvOAMAAUJjRNb83EYIyCevaprxy8hOc8YqCEHzAM4q3fIqKu0DLJuaqRaRnHIPHWrVs5EK5XqSM1WNWIC3k7R2NMpfESYBITOBuGKnuM+aAeu6oGOxtx6EjFWHG91lHILDNZG8fisdLpahYdx6YP8q0/ByFprzkgBc1lW4drD5DgnuO1a/gpdl7cwsRlovlyetctTc9CirWO48FkJbhMn5kI/HNdgwT7NbSAZcR4HHpXF6CfLG3BzGRwP4q7WKWM+WFXHlkqQe1cT3O5rQ4TxtAr6vcS/MfMticj2rltUxHp6RxcRXCByffGDXfeMbdkvDlNqmLbkdsk1xcsSzaA8GMSWrlCO/WtImUolX4dyrNcQRcBopsYH92u/8AElop5wSA2wN7HpXmPhN/7P8AEfB2gtx9K9nvIludK8sn5pRuUj1qpEQZ5pdy/YtcllmXCSRYYgdGAwa6z4c3WVktHBOXbk9cZ4rnPEVpMJQJAd5JyPatT4c3hl1qW3dgjCNcD1Iqp/CNKxseNLJLSf7QuTHIrD6ZFangKJpdGktiwkeMb12nmtHX7KO7sZOhUfMCR09fwrC8JXNppPiP7JISGlAiGDgNnoa5y0ak8CwXKXKRl4LhSsq+nvXKapZx22pFYnDAcqx7ivSZLTZFNA8eSH3qCO1cn4g07F9HKQFGOR2ouTNaGDC7RRNHnktkjtWKXHmShgNrHA9zWg7ywXUkRAbYcMO4HrWbqI3OZ4smPuq9/etYM55rQzdUAePynOT0ZT/SuV1CBYHZ8sGVeDnOfrW9qE0cr+akhWTGM+tY2oSF4TnDkjFdtFnn1tTDkzKucfN396ryqPL+6Ov5U+XAPVkNKVMibgQSP1rpRzMrsCi/Ic568U0sBFmRQvp71ZjbCFWi3Z9KglhV2+Rix/unqKYmyBpccpgfhTS5flgAfaphBzgjH1pvkjz9u4Y+tArkZX1WkGV5XkjtT3QI5AzUeMEUDLEDFwGSQgjqKtW8xEgLqAc8EVnpwcjg1pW8SSqMtjPUDrUMaPXvgnLYajHJpt/aW0k0QLRykc816vp8Evk7l+5Gdq+4r5x8B6qdD8QW0kYPkSNtlycmvpzTbiKSyhdMbCuVx3zUNMZLC4dQRkD096lXqKTALAikYkHgUbCuSGmE0BiRRQxNhS0mKdimgTE70U6kxTKHLT1NMBFPUipAepHpSs1N4pG6UXAXdRvx0601eTTwKES0IZGI5FM3D0p5XPeom4NUhDywzQWyKjPJp1DQDlIB5opvNFKwGCOlPTrTQOKcg5FSwJKQfeNKeBSDrSAkWlIzQo6U7HFNICxpwH2lPrXbAfKPoK4rTv8Aj6T6j+ddwgG0fSq2AYabTn4NIRQA0mq9nzqp/wB2rDCq1kf+Jsf900AR+Ohjw1c/QH9RXBg5Rcf3RXf+OlH/AAjFz/u/1Fedo3yJ/uj+VUiWybGBTKUHIpORVCuPXAYAkDNWFHYdapSqXZQOKtxKYxzzxUjPnH4xybvF133yQPwrgZeCMV3nxmjaHxdcIw++AwNcG3Jp2LiiawXzLqNTzlhV7Uo/9MlXGMcVW0tAbhT/ABKwK4q/ft5l/cE/xc8UjVIyJUKtT7c4DZOARUky5UkCoYh+8FDYmrMt3SkWqOVOCalhwYM98ipLfE9u0B/4DVe0yqSRscFfWpOiO9zrtHxLZGJeSQc1oeHdrarasnG5ShB7mszw7KsEuCMgjFX4/kQXEP3racHj0NcNRO56FNO531mTHc3EirklOnvXSWMoktY7gDcrAEj0Nc5pxEp84cJIowfWt7w+vzXFuCNr/NGD6d65djtWxPq9ut3ChaM/KCMk9frXmk4+zatLazNlZz83GMV6hIHjIWT5lxtOBxXH+M9PSSeHUI0IMJxJjuPWtEyTz7X4JLLUBJGCUXBRvUV6z4dv/tvh+F0cMwAAHcGuH1uzafTh0ZlGUx/EKZ8NdcXTtTOn3hwjP8voK2krqxyp2Z2XiuwS5sjdJzgjJB6GuKtrqbTNftb4jy9rhZAfevVjaRCaWOTa9tdrleeAa4LxloRWNmWP5lO5Rjrjoaz8maN6HqFu8UwcMcwyoGB9iK5XVNNWYu0RPn22drgcj+6aj+Fmv/a7dbGdQ7xDAJPOO4NdRfW/k3BkBxBIfLZ+wB6Gs5lQdy1pl7M2mWsl0fMygQSd/fNMvbRbm2aOVwHRtynHWk0BWt7mWzuCGRiWUddvqK05LP7LNmCVhHIOVPQVKKaPO9c0e8lSS6tI/wB7GuCCPvCuclhZLcSRqI3P3lJ6nvXrN3HNC+8IBxjGOGrmtS0eCYSIVCxu24OByjVadjOUbnkerWqnfJbKRjqp9a5q5uHOVKMpHUYr1LWNDuY/MRvmwRsbHB+tcLrOmzNMfL+SRQQ4rroyszgxFKxzEsgzkoD9ai8xl54Vc9BV2406dX2sOcZJ9aqtFKG2qFOPWuyMrnE4sry+WJSxQleoXNNluflxGrIPapbhNrbd+c9fao2t5NuTjb61Zm0FtdM/ySJuA/iA5FDSFPnjRWJ7kU11kWM+S31NRpG4GSTnuaBcvUl80TN++AA9fSmNBG7fu5R+NTwWU1yypDDI5J42iuo8P+A9a1Fy3kSxxgcFl61lKai7M0p05T2Rx5t3Xk4x61NE5iIOa7LxH8PtY0rSZNRaCSWJPvjHSuILRocPEQD05pqSlsOpTlB2Zs2cqNMHVlJXp9fevpX4fSifw1ayISW8v5lz0NfLVhtF2m1srnLY7V9JfCq+STSkjByrLgEHgUzNncxNnHSnMRVV2Kyrt+4eKnUCpaIHginA80zA9KAeaQySl7UwU4UIdx1FJmlFUxthipFHJpqj3qRfrUgDA0xs092qPJIosDYK+3qM05Zh/dqM0LTsSSmRSKjZl9aCOKicc5poCTIzShqiGRTuKYEmaKZmilqBkLTwMUKKcBWYCGkA5pTilUZoAegOBTyMClRflBxQw4q0gJdP/wCPtPqP513KDKj6VxGnr/pSH3Fdsh+UfSpaARhSYp5GeaawoTYWGMM1Vsv+Qv8A8BNWiM1VsjnVz7KasA8d/wDIr3X+7/WvORwqj0Ufyr0Xx4f+KWu/9z/CvOQwZI2x1QVViGSq2BT8ZANQE4OKmB+UUAGMMD6GrG8Fc+1QRjeSM4qUR7P3hcYHOO9DGeE/Ha1ZfEscrbCsqADPUV5WFKsyN1DGvd/jHp5vbG41NIiREfkz2xXhZVuXYYyTQikX/D0whvt5RX46GrMRjnvpwTjeScDtWMrMpO04zxU1tJ5UisM8frSZpTbuaX2R3SZFXOzp71kSLtf5eldNpV3BJNneM9xWf4itFhuzLCB5cnzYHao8jqlBNEGlyFZlY9BUmoxCO83DhZeR9arWXQ4PNaM6/aLEn+OPkGpldCSaRpaVINkUncfKw9/WtxR9jZiVDRXid+zVy2g3AbzI3OTnco9a7UOj6Wu452rnnsa5ZptnfSlobfhe7lOnLFKo8yA8LnqK7G3XasN7A33e3seteY6fqCwXUdyW6/eHrXY2viWGCLajKyMvcVk4HQpnbI0V1ZlQeAcg96yb9YBG0F6fLMg257HNcdqXjCRCTG+BnII4xWJqniuS7/dtcP8AMelStAczUuWFlO1pOwJjP7tuzp3H1rkNVhhj1IeTIAjHcpJ5x2pdT1KadQjsGdeQ3PFZ00jyzbmYkEYb1rqhaxxSd2ep+CvEom0xdJ1F13KP3E/c+1dJqiC70sc75kUn6j0rw6C7mVlQECMckDr9a6/wz4rurNzb3Lb4HXCuOcfWomtS4tjrqKfw5rtrqFv/AMe0uPMwOh75r1/Sbiy1bQwY5SUkT7h6rzkVwsN3Z6pYS2spBRxt+YfcPrVDwnq0/h3VjpGpsQrH/R5u2OwrOUbo1pvU9LtiFVZmXM0LBXI/iA6GtUTLMgGAUfgMPWsW2lknEMltJuK581G5yD6VrwZHKFV3AYXHFc50t3LlkFnjaORQ235SKqanpUe4NEvyngqOeKnVCkX2mNPLlBwwHetJQskAk7EUJk2OGuLXdPPakKQrAqCMnGPWuP8AF3h6BoDOse2QNg7epr1TUNOjeXz41Ib27muT8QwXSx3KyWwmReQuefqK1hUcWYzinueG6tZrbu/yuw6A+ntWBcPbB2V0kXjGRXf+I7PcGkR2X1Eg5zXEahBtO92VQOpPeuylU5jzsQrMztkMak7A465qNRLMSka9uKnt0N1KAigRKeWx1rbtrS1hj34GRyTXTc5rHNXLJap8y5PcVPoFrqGvaimn6fblt7AHA+6KNThk1CfbbqN6uFG3qxNfRfwa8GQ+GPC6X13Gv26Vd29hyPas51eWIUKMp1PIf4J+HtjoNoJtQCGVl+VcdTXZWNpb26EvbBcDKjHApdOspp5vtFyzPnop6Ctx7YtAyBcArXmzm5H0NKlCD0MLWUtNS8OagiFHUwMMDpnFfFsrf6RPby9VkYD25r7V0yywl1Zrj5wyr+NfGni2zew8V6lbSDDR3DZ/OujBzb0ZwZnFXTKlqXjl5PI6V7B8ENUl3T2ZDbIz5iY5yO4ryCF1cjI+avWvgxJbwXucqd6leRyPwrvPIPbnkVrXevIPIqaKTKKcdqpW4zaqvrmrUHCD6VA+hNu9qUHmmGkzVWJZYBGKcDxVcNinBqmwEuaMmot1G6jUCYSgUvmE98VBmjNNIZKzNnljSbj2NMFFUSSBs0K+DTAaQZzQMn3qR7012xUYJpCTmgB+6m7qbn2ooAduoptFAFIHinj7oPrUSnipR9wCsgGmnJTTinLQBMp9KDnGajzTt3atEBasP+PlPqK7RCAo+gri9P5uE+ortFHA+lDAeCMVGxFOHFMbrSsUrh71TsuNZKnqVJq52NUrUj+3x7KRTJbF8djPhi7A6hM15uhHkQ8/wCvTPG6k+GrvH/PPFeYr/wAe8WeyCrEKTlwc8VODkcVEvTNTJ0pCJLfgmrBjJccDNRW45q0OwPJpMDF13T01Tw1c2xQc5K8d6+XvEGnvpt3LbyAhlcnb3AzX1mqNloM8eZk/jXkXxw8JxLqKanC6xRkbZnI4A7UuYuB4kev41KiZIGQMnqakuIlEyiI7xnblRxUsaiNwsinBHek2aqJH5c0EgO1l75FaiP8AbLYo+RhcDPrTI/Jk2gsuR0yetXrK1jaTaXUFjxg1k52OqlT5t2YO1o2wOCDg1p2WNu/cCMfdB/nV/VtGZlEkA5Uc+9Y3kNG+4ZLDqKXtOYcaTjLXYddQzWc6zKCqscgitbTtTe4tHgLnefQ9aLTy5l8mYFkkAGf7hrNvrG40253KS8eflcdDSaRuoOJoNLIpwSeO2at2ss9yDFG5Q46iodLks78KsoMc3f0NdAtgkEf2qzkiyow0eetcsnZnRAsafo8E0Uf2pnbcOprQTwvYiQbZSqd/Wqkd9LdQj/lnKvUVYW9uAv7yRBt/CsW2dCijQg8KaXM7GTfuXjJbqKzdV8L29tIzxNwSNp7fSrcGokHcCSO+B1rSjvbW9CxBZDxg7hinGo0TKlF6nDXOnm2uhE4Xy2Oc/wB010mm6QL2MRKo8zrGQAAT71fn0Ayl1GZFblWB5Wqehf2lpty8J/eR5Oz1zWntLmapl6yQWHmWWoRNBJnCvjrV2bREvoWt55CQo3W7Hk/nWza+RrljsuIwtxGPmUj5s1RltbvRELSr9otyeo6pmpcxqNiz4Oub3S5EsdSOCG+SQc7l9DXfbo3/ANWpDHkA9PwrhYbm3uSrq4CgDDjnafQj0rpLCdri3Ch1WReg3dcdwal6lnRWzLLgMevH1qwh8ndGnKHjBrHs7hllEgcb+jIR/Kr73CSIOdjjms5aF2diSWRo40I5O7nmsTWpdxLthcKa0bmYNAWz/wDWrzH4k+O7TTXOm6cFu79+uOkY9TTh7z1MZNLc5/4hahZ2SKZ5MOQcKvJavLrpLrVZPMYEQqeg9K3I7O91C7N3fO0uTyzHI/D2rS/s4QIfLIA9AK64SUNjhqrnOeiiWGEKnCjrUrhbpBZxQyM7feZegFa1ho1zqV+LSzTcT9444UV6t4X8F2GmWcbSRGSVvvE8lj/hWksQrGNOjzyscp8MfBAu7+PUb9dkULgxrj72PWvbLWdEAWWFmt14GR+tUdMt4x+6EKRoOy10KiOWLy9gwOhrndbmPTp0VBE1rNZyoPL4HvV1T8pAPGK5q4xby5Ukc+lWrLUA5Ee/ms2bqDtcdOvk6uhHyh+uO1fJHx1tRa/EvU1UABmDfnX1zfqJZ7XHUyda+S/jvcC6+J+rFGDLGVHH0rbB/EzhzFXijhImKyKR1zxXrfhWyS7sLfUtOkWK+hXc6qcBwOxryq1iEiNnrXcfD/UmsZ/IZjskGK9FnjpHvnhK9Go6THK3EyHbKp7NW0mAK4fQLprK1g1ZBmF28u5iHYdA/wCFdpG4cB1bKMMj3qFuJ6EhIwaTNB5HFJg4q7kjs06osn1NO3Ad6YD6KZvFG8UASH7p5pB9abuyKXNADs04GogaUGgCSjkU3djvSFjQA7NFMyc0pOO4oAfRUW+gyUAKX5oqItzRQBAuKlBGKrI+Rxx9akDVLQkOY0qmo92TTkJIpJDJ8ikpo6Uo6irAv6f/AK5cf3h/Ou0T7o+lcVpvM6D3rtQCFH0qQCmnrTqaetUNMD0rJktpDqpuI5ShUYP0rW9KqoP9IkoJkV9fkkPhq8Rz5nyZBrzqf5LePnB2ivRNaXPh68Gei151qJ/cp/uiqJEim3DavarafdFZtp1zWlH90Uhlq2qc5zkde1QW9SyOiKWkdUVRliTgD3qWBXkkjiWWe4kWKFeXdjgBa8P+JPi2fxjfvomlkppUDYeX/noR/SrvxN8Yy67eNomkzFNPQ4llXhpD3rnrO0S1iS2tkOT1bua56s1HQ1ijOk0u3S0WCFQJVz06fUVh6uk0aCIgEr3HUV20MFzd6imlaTbiS8k4J6gD1Jr0pPA+meHfBt5LdpHeag0BaWR1yF+npU05OW5rHc8S8K+GpNXtvtBBMW7bnpg1U8WRrouqpaWm75CMlvWvRvhlOkVo8EiqN7EqMe9c18Y9Duo9SXV44maCUAHaPun1rZcrLlzLYj8Pas15brFeQmIscIxGAabd6cs87tGNhziuT/tK4WDEjgt0THVcV2dhM+oaVHcKcTRjEg/rXNX93VHZha3NpIu+GPD/AJ7qkpZJAc7sZBrvR4XtL7TDbXUId0XG5RjdWP4QkMhhDHOD1r0PTUzD0Oa4nUkeioo8b1HwY+n3sipCzQHlXXqtJp+nC3fcbjefRq9nvtOS5QkghsVx+v6QtursYhnGQRWblJm8YROOuYkjjedSVbtXPXs8nmbo5CZWOMVu6sT9nfnGDVbwxpqzyJeXKHaxwPb3rai7vUirCy0JtN0jxHfoDaxGJSB/rnxWFf8AiPWNE1KSyebfNCcMRyM1794c00LBG6AHI2gsPavnjx3Y3em+Nr5bpGJ83ch/vCvQp0oTR4tfEVISsjf0n4nX9rhLy2STp1X5sV2Wh+LdD1WZGIEbSnDdxury3Tz9qeQXFq0spTKrwABWt4V8IalNG8qBo8sSuM4qa1KMFoXhK05z1Z7RHplu0qT2kjRzJzvRuDXQKsUkIinUMSOcjOa8x0i61rR5PKnjkZQATjkGuz0zUnuY1ZFyW5IIxivPlI9VxQlxoO25Z7BmspunzcpLVrR98khtbuDy7mMYYgYDD1FXgZpGhVgCpw2QOlarwqxWRvvY61m5MVio1puKtDPINv8ACx61NHdxJAzXjpblOWdjgEVV1rU7DRLKS+v7kRQIOn8RPtXlmu6rqPjCYvOz2Okg/u4QcNN7mqUXuyXUT0Rc8a+ObzVjNpPhnctuMrLc4+8O4U1zek6DbpHu+Yznl5H5Zz6GtuOFII1htbcRqowB3q1Ywssg8wliTjaOtJ1ZbRIjS1uzFNuYlZAhWIccdAas6To8upToJEkSAHLsO9dH/wAI9OYGu5VZY0kyYf61uaJHGVQYwqsfxBrRMUoIu+GdF06wtUkgiVM/eJHU10SWrSZ8ohS3XPejS4VSBOMjJOCK04hgDAAFEmOEFF3RhWcb2E8kch+UtnJroLL7PIuFkCk9xVPUYS7ZXg+mKzPOe3mOWOM1MUavY19biQ2zcA4HWub03f8Ab1AJ61c1PUWlt/KTl2OKu6Jpy2Vv9tnZiSM4PrVSdjSF4x1Ld03kzQtKu0QxtI4NfFniy4+3+LdWuic+bcP/APWr628cX8lj4J1nVZWCstufL/HpXxuHL3Dux3MxJJx1NdeDXU8rMZbILPCx9eT1rWs5DEUdTgiseAc4Pc1rsNhCj0FdzPM6Ht3gG+hudJaG7w0Mq7WA/Wuq8PTvBPNo87bpLcboj/ej7flXj/w91Ax28kDE5UhwPUV6TfXDeRaa1Ecy2x2v/tRnqKi+omjslPA70pPBqCznS5to50xtkUMPYVKTziqRm0FGabRVAOoptFADgacSPWo6dQAZpNxoxSUALkjoaTe3rQaSgBdxPU0UlGaADJoyfWkzS0AFFFFAFW+xCU287qaJDS6yhjCMvReDVATn1b8qckZpl9XPpUiNx0qjC7E9Gq5bnuamxdyyh4qSq9OU8ihiuaOl/wDH0n+8P513TAYXntXCaWf9JT613I5Uc9qSKGsKjIqTFNIqgEAqtj5nP+1VsCqpHzP9aAK2s8aFd56FDXmWoP8A6PEcfw16B4v1S0sNGlguG2tcDan1rzu5Ie3jwc4FUSx1kcitKMZXqAAMkmsiwf5ioHNZ3xNvJ7TwNfy2zFZNm0EdeeKQIr+KPiboPh+XyEL3kw4ZYuimvOvGXxavNfsP7Ot7P7DbSN+9ZXyzD0z6VwEUIkcHYZXJwQT3q+ljHay4Yxlj1RVyR+dTJpGsKbnsTafqcUYIDpH2BYfrXSxK62CM2qWEbyL8rb+c1zmmaKuqaitra28mCMlh91frXSP8P9uBHehgOzLxmuScoN3N1h522Or8C+J9N8MWzIujR3Uzn97cRzBmPrjNdD4p8faBqXhW5tYpZobmZQqpMhHH1rx698D6xb7ntSkuOQUfB/Ks2dNc06RIL9JGXrtkGcU1Ui9ilSktbHTwRXVuyTWlypHXCnNX59T1O7tza3DIYSMFWGa4m3v905e3aS3YHHBOK3YtTvFj8y7hDxDGZUHb1NYTUuh6VD2bXvIB4dspCWMW4k9av29gljEREpCtwea0LBop4A9u4kGO3UVPIhK4deDWDc+p0OnT+zuaHgqFnnTA4U5Ner6ZbKkAyBmuN8D2KLbo6n5jyT2q14r+I2jeHAbW3kjvb4jHlJ91T7mojByBzUdztNi4OQMVgeIIIZFwXiUEY+ZwK8k1f4pXVyW+1XTRq3/LC2OMexNctd+N7Wbcf7PuJSOnmXBPNWqLE8Uo7HSeK7aMNPZxXkCOWyCr5GKoRanNbxQxLHE2wgEq/WuWbxOJZBjQ7XJH8WaifXNPfH2rSUiUdWjPNawpuJMsTzKx7z4R8aQfZRFLC3A6A1B45stI8ZQKrWbpcpykw6/SvHoP7IntvMstQuLaQ9g3SpNPvPFVlIZLDVpJ4lyxYNu/AitlzdGcbcb6o9K8H/DzToJfPnjnnKngseleiw2FvFAsUaKqL0CivDtM+K+tae4ivoUnXPzEDDV6D4V+Jvh/VWEU8j2cp4AkHDH2NZzjVbs9jopVKKemjOqm02GSRnKk57Vp6Zp0MQDCEAelPslSaNbiGRJo26bTmtNF7AHFcrTudfMmMWJABhQMdKwfGninT/DFmZJs3F0w/c26cs5rL8d+PLfRFOnaUq3uryfKIlGRH/tMe1cfoPh3U76G/wBfupHv9RjILk8hAey1UYa3ZhUrKOhTura/8QXf9r+JJH5Obe0U/LGPQj1q4YjkF24X7oH8NaAs3CmS4Zkk6qpHJPvVnS9Fu9WnEUKAR/xv0A/xrOrJvQ1pQSVylaRy3lzHBaRtJK3GccCvQfD/AIbi09fPulE10w6kcKfXFaOg6JZ6PbhLeEbz9525YmtKQg9qzS7mkncyLmEDzt4+WQEH1ye9YunwCOUwMTkDArppV3hs+uOazhbeXcZxk9c+la30Mm7mvppzaqDncuAc9/epHmKsQOcdqjteYl+b5j1FRamzJZM0QzIx2n1oTuCZJc31uwDM4UqOaoW8P9rMxiLKueuOKrW2kz3Lr5rcHk/NXTW4tbK2EKYyOgFXsXdFS10a2tCJJW3svQ026klu7nylAWFfyqw8jSNyeKratfafoekz6lqEyxQopZiePoBSS5mDnyq7PLv2mvECWXhm20GGRRJdvukVW52L7V83I/zA9ugrp/iX4iuPFniO41aVvk3FIV9ErlkPzDivYowUYHgYmr7SZJ9xvxyK01PnDzMnAWs9EC7WfpVuxk2o525CngVTMjrfBUyRRyXDHLxHDjHVW616rorNHaLCQGtpgVKnnFeQeFpA8twFGC6DA9wa9c0LzGtEjfgbMKfoKzYmanhG6ME02jOcm3+aJieqHtXTD3rhr120+5tdVj4aN/LmHqprtbd1khWRW3K4DAj0oRLHmig0laEMM+1GfakzRmmAop46VGp4qQdBQApptLSUAIOtKcYpO9BoAQ0lFFABRRRQA6iiigA1hRt4qvbKuwZUflVrWASnFVLFw0a+xwatmSVjUtrSFyfl6D0plzaBWJRSv4U+1n8uUAjO7itC4lRVTcAQ3XipsNMwGBViuaATmpZgGuHPbPFNK4NKw0XNLJ+0p/vD+dd2oO0fSuG0sf6QuPWu4ydo+goKAimkc0uT60xsnH1oGPWoP4ZD71YHWoU5Eg/2hQI4D4uc21l7SH+VcgkmIME12XxewLaxH/TQ1xI/1aiqEWtLzvzmo/GmnnU/DF9aKTuaIlQO5FSaaPnrXh4YEjPapbA+ZtK02+nnCRtGJEBDc/NwcdKs6DoN7f3xjjPmMzESMf4RXUfEPw5d+HvEM+q2i4tJ2LqR/CT1FVfB2sxWepLK4221yMOfQ9zXNWvY7cK0mdjo2mW+jWgt7dckj53PUmrqjNWY4VbL8Op5UjuKcIBnha8tp3PWU0VdpPPeuV8dH/SLdWOflPWu1SHDjg+9cX4+2/2rGo6KvFS5Nao3pRU5Wscouj2k9wjM5hDEbiDVK31K8sro2E8PmQM2FY9CK34UO0HFLe2iXts0MoCkDKOByDTp4p3szWvgbwcoHJXl7eaZetJp++EMcleorRt/GGsu6IzQHA5ytZGoTSQTyWU0Zdo8APn71M08zNJn7OQB0AGa9OXLKnqjxIuanozurzxD4oubY2VhcRwQsgDSINuM+hqnoWkgTiAot1cS8tJLyT71NpDJNY+Q37tgc+9Vre8k0PxI9xIWljlQIcH7o9q4nN8tkj0aFKE5rnZ3Ft4W0ZQJLizt5ZsfMccZp76LpCAiPTrZR/uA1R0rxLZ3pwsmCTjnitnzVZMggivIqVa1Nn1VLCYeS0RhX+jWhU4touemFrn7rQoAxP2ZMf7td1MVMeMCs65UYIAH5Uo4ur3LlgaL6HEvpOnmIxNbMhz1WotP0i802bztNlLg9Uc4BFdbJbRuOVwfUU1LdUFbRx01ozlq5ZRlscn4g0mW6CTeV5U2MlSOD9DTvCrWdksq39kJJ0OUDdHHoK602wuV2MCcdPas/VtEaCL7UhLlT93uPeu6jmD+GR4mPypwXPA6H4f/ABEghvltPsrWkZJ3o7fIB/jXovi/Vrq+8NO/h2+htTIvzzMwYqPb3rzfwB4Om1W+i1C2thMkilJvM6EnuK6TVdEXw9fw6VKpt7ZmByO7V2tQlG55NOc0+VnPeFdDJbbp++9vbgnzrhxyT6knoK9n0bX/AA34S8LDRpXimvvLLzquGAf0z3ry5TNaXUllYLIGYlFSPrIG9SOldr4T8GJA6ajrGJbrqkXVV/8Ar1ze0cdzr9jzLUoaHoeoa7dPqN2jW9pI5dFZfmYe3tXe21tDawLBBGqRqOFAqwBhccccADtRisJNM3jGxGQW+UenFMlBB298CpOhyKYSSxJOakojAw2CKiuFyq4xxnPvVkqWOaRgAp4HIp9AehBAR5WR8pHXPenWduNVvTGGdYY1y7KetVbyQ28DFeQvUU3SLm4s3aeBd6SrnbmmjOW2h2Om6VZwW3lKPNGPvsfmrFvbRLe9MSuXA6H0rbtL6F7OOYOAy/fU1yPjPxDpvh+wudW1KdY41yUUnBY9gK6LOSsjipuUZXkWdWvLPR9Nl1PULhI7aFSWJIGfavlz4vfEW78Z35t7aXydHi4jjBwXx3NUviR8RtV8Z3DpLI1vYKfkgXofc1wpAzkcV2YbDJJSkc+KxTbtEsrIBbBOcg0iDvUK1NF8ylR97Nd1l0OFNvckZiUA96sWYG+Zc4yOKrEYjOeoNOtXdZx3z1qGi0zd8NzmK7QZwemPWvcrNTLYwTQ44UZHvXz/AGMqrqSgkrgg59K968Lzi5tGiUHaYd0f144rJoGX2gF5psy4BLKTz2PpWj4flEmlRkE70GxgOgIqpCGF0qn5Y7iMnPowFSeH2hUzRRsM5O4e9K5NzcjlDJz1HtSlhUOCsxXouOlOQYzWiJaH0lFL2qhCrT+1NFPHSgAFFJRzQAtIaMmkJoAD0pKKKACiikzQAtFJmigBmsT3WwYtyKz9LlYo+4gNnp6V0GtJhCQO1cxprHzpgTn5q1ZkbkDtvGT9K07kloIznmsVHOeK0jITEnI4pDRXk/4+GH40jjk0r8zZ9aJOpqWMt6V/r1/3q7VCcD6VxWl/69f96u1ToPpUFIX8aQkUpFMOO3NMYu7nrUUMg8x0wfmPWnY5zTIV+ZzjnNAjhvi9yliP9uuIY8AV2/xg+WGxY8fvD1rhN7E1Qi/pxO4VsQcsKxdOJyK27cfMtS0Aa7o9trelS6fc8LIuA3dfpXz5rujXHhjXn0+7tpJLRsrvAz8ufvCvpZBxWZ4m0Gw1+yFvfIMrnZIB8yVnJFwlys8u8M6s2mRxWF8TJZycW9yDkAehrstoChlYMDyCOa858SaJr3hAyQS2rajpMjFg6DOz39qd4Y8Uz2qD7FILu0U/NbyN86fSuedFNHbCvc9GRMgseAozXm3iPzJtTlkb7u8hR6Cu1PifSr3TZBC7QXBGPLkGDmuS1m3ZEjmYH5+/Y151SnKPQ9zLUneVyhbj5QCKlK5NFuvHTmpSvNcOzPaUo8tmcN4xjEd+twB1HzV1/wAJtIGrzSXEkf7sEBeK5Xx2Cs0cfBYg5Fe2fBTRzZeE7V2ALyfM1ezGT9nqfN8tq7sWPEfgKG+0ySXTVEF4ifK4H3+OleYRWAvrJra8i8m9tT5UwY85zwa+nbC2IQMcY7D1rzr4teB2vEbWNJUJdKPnVeBIPSpsmW42ldHh9lHFaaikV7FIFVtrFRyvvXY6fcAKymYOqnAZT2PQ1n3kNtrFszwo0V3B8siEd/Q1haLLJY619lnVkRyAyk9PSuevQU1c9TBYuUWkd4JQUA3DFMfkVRljeM8K4XtkVJBLuXazV5EoODPoVUUlckxQEz2p8S7mxmraQKP4j1qdB6Mjs4jngcVe+yLdW8kTgoQpG41NptrGzZPUVqQ24AdgflAprR3Mq/LyWZl+EPEP9iaUtnGrPJA5ZCMhcA1Q8aeNZ/EMklxc+WsoKiMIMFDnrUeoRDbMVTblgcAVjeDNGXxD46FpBG3kxyh7kjoFBr28LU5qZ8biaKhWuj33wh4fsdL06KZczXMyBpJX6nI/St1VAGAOKIYxHGEXoBgU9VYHJrOob3TQgX2pripec9KZJ2xWYPYrYOc0jffIHapCKYRgkjvTAFzSSEAdKVDg0yTJJ+mKAZmanMq2Ushx0rM0zWYbW1zdKxjAyMHGKteICvk+QOrDFc/qIC6eUPQLjmgUbGd4x+M2gaLEYrK2uLm85IUcL+JrwHx14x1jxbqTXepz5Qcxwr91B24/rUfxCbHiGcgjI4rnxu4zXs4eKcU7HhYmq3NoemD05ND8NjpVuMLsBC4NVZ+ZK6UrHJqLFgsAaejbJD25qOPhgfSnzjEmfxpjRPIVQk45x17Uy3bG18/MDzSMTJbEjllpkfQH1FS2Ui6jj7YZete4fC3UDMlo74AfKcj06V4VCe1enfD64ZbJRE3zxnenPQ96hlM9e8sLdhJAPkYsoNZX/Hv4gZoxt8xc+xIq8btZbWG/U5DAA56io9Xhz9muVHKsM/Q1NiTVhkaaMmQYbP51KD61VsnUqoB4x61bxzRcli0HpTSaM5q0Iep96kU9qhUCpgBmhsBwxQQMUlO7VNwImNJmlfvUYPNWArMRQGyKa54NIrcUASg03NIppaADNFFFAGnq/MBrkLBsXMo96uasdUdcyXm0+y1laW489lZiS1dDRkbcTYORWlCcxVnW3LmtGAZjI9ahghG/1gofpnNSSAeZGaZMMsxx3rNlIsaW3+kIP9ofzrt16D6Vw2lD/SkH+0P513K8qPpQUhXPy4qBiQODUz9qgk4bFJjHAkjHeoFWZ5iUfaOnFSp98fWnWg3PJ7HNCE2ef/FqJgLBZHL/ADE1w44Oc13nxkxjT8dNxrgM1YjS0/qK3IOq/SsPTvuL9TW3b9VqWBqqPlFFM8wAYwaUPzwKmwCSxpJE0UihkYYYEZBrhvEXwy0XUJjc6bJJpl6x4kjPH5V3oOaCMn39aCr2PCvEHhDxRooD3lvDqNuX+WSP/WGsLUL66tIvLMeox7f4Jo9wH0r6B17Ms1kgHIcnmsXxRpElzp0iA4Yp3ArmqyV7M9bBKSjdM8OHiec/6xYxjsUI/OnnxJK4KQxLLIR0RDxS6kkuia9DLdxpJHnDKyD9a9U8Oro1zax3dtbWyeYOqxjrXLy073sd8XV2bPMtC8KXmsX/APa2qRPFEOgfv6YFe9+BoVi05I0AVVAwPSuc1cKsICEYHStvwVeBkWLPzg4x7etROtf3S4U1F36nf2vMQp9xGkkRSRQVI49qr2kyDCE1Pc3MMP8ArGCgd80KRR5f43+Hctzftq2iOI7r+KPoso9DXl+vWts0n2PUbK4tLpDgO3BB+vcV9HTa1p6n/WMc+i1j67b+GtegMWo2qzAjglcMPoaTkifZO90eKaLqUiWy2OqjcqjCTjuO2alkituXt7qOQfXpXR6z4AWySWfQdWXy3H/HvcrnP0rhrvwv4qhLP/ZCSKed0Un9Kwlh1M644mcFY1oJmVhxmtOBwQAK4V7LxJCwL6NfKvTKtVy0h8SyFUg0i+LE9XY7azeCRvHMvI9EsJre2AknmjUEetMufEEDZgslBT/lq5/kKwtH8J+KLp8z6csRPQseB+ddx4d+HjIoN7dLxglVWp+rpBLHc3Q5QR32ozx2FhGZJ5TycfdHua9X8CeErHwxphhiUNezHdPMO5I6Vp6PpOn6XHstLZEP97HJ+taS1pFcmiOKpLnlceoFO7UwU/PFMiwHrTGGaeaY1K4uhERUZFSmmNRcCMDmmv3pxbFVbqUop9KBNmJqzebqCrjGBmsPxN8lo+OOK2hiW8aTPQYrA8XSBbItzyTRfUInzV41y/iGfcc81lMQxBxitXxjx4hnz61kDlgB1r3sPpBHzuI/iNGm/Ea8dVqh1kYVblZvIkb+6tUh61uZCgYJHWpZTujT6VHHy2KeJSFZOwpALFkEqCcMKQnaAM00sMjjrSvnsOKVhokRu44rufh9erAkmesZyR6g1wI6cVueFr/7PdkFlKPwwIqGO57ppM3nQxJu/cv0+prUW5abSbiLJE0JCk+4rmfB95CdPgg6NI2VHpit/Tk3TXIZT5UrHJPrjHNQOxs2zIVB+7uVWUelXQ3HFYtjJssYi2XCDbkD0NaVpIJEJXpnNVYhssFvagH2ppJ79KOaoQ8H2qQNxUINPU8UASh6C+R2qJj8u6mbuKVgJGc00HmmU7PFMAPPaikzRQA4HHalz7UyigCTPtRUeaKADVF+TJ54rm9NH+mt7NXW38YaPI7VyNodmquAcDNdDZkdDb8Gti3UC3JxzWJEyk8Gteyl3QkE8Cs2xosuoIX5RkCoZVAzUnmpszuFQSyAjg1DY0TacP8ATY8f3hXbLwgBridJbN7ED/ert26Ci5SEc5xiq8x+epz2qvLy+RSGLGMuPrUtgPnlPvUS9R9aksXIZxg8t1ppEs4L4z/6nTj/ALZrzsE5r0T40AmCyI/56GvOx702JGtpx+RfrW7akbh9K5/Tv9Wv1rdtckg+1KwzQ6rmnR8ZzQoG0fSgUmBIp4pwPNMXpSqeSagLFS7G69tgcdTVy+twbc5GeKp3Uix6jaA8ksQK3L1cW5BABrlrayPawekDwT4s2IQNIq8q2RxXLeA9fksNTFlcO4hc/Jn+8e1ejfFSCZ1YCLKEZzXkGpWk9pPFMUOEIYH3rKKXU756JM9ja8MsfsRk1TTUbiyuvOtJWRh6enpWD4c1U3Wl8NuYKBVuKUFiXxk1xyj7xurNXO1s/H1xEF+0WZlbgfKa0z4xub4qI9MkUHu1cJp4El2gUK1dpE0cUagxjOPSncSg30NSwu5bw/votjDtWkkakZKqazNNYO4IGCa3ljUqBigautzKlsxI+WUH046VIlqAoAUcDFaZgX3p8cJH3R1qhOS6mS9o7KRjr2rN8maylLEAxk8j0966ryn7rVO9g3DBH1qWK6QunzK8a4YMpHBrRixuytczCzWVyAP9We3pW/azK4V1PBqLjvc0VbinhsmqyuCOKerY70CsiwGpwNQxsDxmpBSbJZLTWo7U1jSFsNaomOaexNQO2KCLiP0zWVqszbSF6ZxV64kxGRmsiZjLOqDlQeaAQlrEEQk9SM1yfjFwLFgTyGrs+G3EcBePrXA+P22wMRx83NNLUaR4B4wTOp3Eh654rIsgfOyewro/FUO/WTEqZ39BWVHZyRSFXj2svXNe5SkuVHgYmP71siuNy2xUnluDVNfTPSrd3lcK3UVVIK8nvW6MLD4zhwTTpQFYnHUUz+HcPWnzFWjXb1HWmBEfenx5fIyOOeaSUDecU1cCgVyaTBbI6UW5McylTt+bk0wMMEE9uKAcgCkyrnoXhnWJLW6ilQAREggehxz+depaPqEEkZjBLpOA5IP3Grw/wzcedthYAbO5rs9Ku7rS7iMpIRuboPutUNFHqWiyLHHLaynDBjgH09avQRNC/wC6PGMkHpXNwXMc1yJ8FTKoHXqR2ro9OnVkw5+boR3ouibFkHIFOANMf5XGD8tSZwAexpXJYdOtOBFMJyaM8VQDmPamZoJppoAeKd2qNTSk8UAOopueKKAHZpC1ITTWIoAduopi9etFAGlegiJ/rmuLV1j1OQswA3d66O/1JnjYJbPkjHWvOtW0LxJeaqbmJQkPQDditWzJHaLdQ4GJk/OpZtWigj2q6kHjOe9chD4Z1Qf62ZAMf36sJ4YuicyXMeP949azbNFE66xuxKgbd09+KvLMuME81zVlps9tAE+1IfUVeR5Il/eShv8AdqLopxOk0mQG/iIOfmFd1ngZrzbwzN51+g4wGr0gntVkik89ahYck+9PPWkPSgYidealsCCG2/3qi6Cm2UD+eZFchB29aaE0cZ8ZB/ollx/y0NebBeeRXpvxiGbWy/66GvOSgFPcktafxgds1uWRwlYtkOQB61sW2Rgc1LGaiH92KUVGp+UU4GiwEqGnLgUxM0+oYIydcDfabOZcgK/X3rrBG1zbIe2Oa56/i823IHO07q6TRpA9kg9QK5Kqsz1sLL3Tj/G+iLeW7xjhgOCa8j1zS0kt5beRQJE+Ukd/SvovVbZZI2Urz2rxnx6qWeoscAB1+Yf1rFrU71qeb+GJfseoTwOSAGworo7+QRMjKMhq4zVLsxa2J4xt7H0PNdFbXyX8aIpwRWc46m1KVnY0rS9aF1kTIYdxXXaNrLzRHzwPqa8uW8msbwrNh4+cg+lejeGIIr+xWeziDx9ThgTUch7FNR5dTrdMv4FCsWIPvW5FrFucDeufrXLRWjnC/Z5xngYFXYNA1SZ1WC1bJ7scU+UUoUZbyOqiv7ZsEyov41dgu7dh8rrj61zdh4Ov7gHzLnyiDjBP9am1/wAPx6Lpi3FzqDE56A9aPZtnDWjSj8LudIbu36F0H41Q1G6hTnfHk9PmFYVvc6BFpZn8+SeXacfN0P0ryC8sPE+qa1OEvJFieQmIBjwM0nTsYqJ7LcOkqk4BPY1PoTuUIJ43VzPhqK8tLZLW7mMjAc5HSus0VBsOB3rKWg7GrFnFSc02OMj7xqQIOuTU2Ex0PBNTqagUYqUHFFjNj88UxmpC3vUTNTJHM2RVaVu9PZuOtULq6VFI60rCsMvpcR4ByT2FQ20QXr1PU1HBl5Gd+TjirnCoAB2oGRXCqsYxXnXj/LIVXnmu9vpCeM4FcVrkYlvDu+cZzTTLR5lY6N/aHi2xtXBAOWLH0qh4604prxcbVgkZkiI4DbcDNej+EbNTe6vqrxljbQGKH03HisnxVp32+7ttHVVjfTrMTMT3duSK9ajpE8LEfGzyDVLWSO4Pyk4FUHznB7V6Zc6OLyyluEjPmRAB48c+5rj9X0aSLMyJ8ntXRGRzNGJjEePekXv9KWQFQaYhYuFGPmGOa1RLAtnnOc0n1pCm07c/dpTzQRcTJpyk0hAoBxSauUmX9LuTbXKvgkdCK9L0G4W6lhVmRgwyufUdq8pRiCK6TwveSxTx4fhWyBUtFXPUnc6cYr1fMls3k2sp6xtXW27h0WaM5ORlgeorB0mSC/sHicBo7hckHscdRVrwdLm3nsJCxeBtmT3xWdhnUZYDJ6GpFl3qq/Wowd0AB4INNts9T2JFNIgsg460hPNIcHvRVgIxOaC3TFB5NNbpSbAcCc04mo1PNOPakmA8GlzTRS00wCmsKdRTAAKKKKVwMl5HYfMx/Cjcxx87GmnOKFB9ay5ma6dhxLngsSKljBI70yMc81PHgVF2DGskmPao3UhSfarLv8u3mo3wVP0pq4mTeAJGk1Yq3ZsV6tivJvhyM605/wCmlesk1rFktAelJQTSbqskU9Kfp5/dsPeoiwxUmnHKmhA9ji/jD/x62X/XQ153kntXo3xfG62sh0+c154VqmQixY9VrZtuv4Vk2qgbceta9nyM+nFIZcB+QUqGm54xSqRQBYTpQ9MU0/GaTAYQGRl9RWj4alHlBB1VsGs/GO9JYTi21HrhJOce9c1ZXOzCzs7HUauwEWUGXbtXn2veE01S6kmvVwGGFGelegKvmr5jdewqrdpk9M1zo9eDPnXx38P5tPf7TauXXH3TziuL0ed4btrRgUdTX1BrmnLdwtEcbiMj/Cvnr4jaLLo+sLcpGUG/BPbFDRotHchvrc3DhwARtxitLwjeX+hXkjWrZU8srdD9KzrKZlkjMjDay5FdJFBGVV0wS3WoufSYD2dWFpnWQeNdRkjhcW1sT0OWPFbUfxHvYoGEWlpuK4BaT9a4mKBFQIFxmtGzsA5G9wMjjAoudU8roydzR0zxd4osg4E9s4lcuNyklc9qs3lxqOqlJ9SvHuMnlSML+VQ/YlgSJXw4Xg4rWs7WaVUiEeIx04qXNmMsHh6Otinb2cCjy4Ycynv1Fa+maQyFnkU7z3x0re0rSYYVEsqB5fU1fdcDpxWbZ5uJqxvaCOaa1dJAScjvWvpbKYlAGCDzS3aBuMUy1BjBA49qxkcLZqhqeCMVUtnZuD1qwKRD3JKUnimA0hkC80xMcTio2NDuCuRVC6vPJBYYJ7Cgh6DtRuFhQbmI9qy4w0zlyeD2odWnl82Rs56CrsKJGMk8HoKAESIJjFPc/JipDg1HIDjAGamw0Ur0Daa5DXP3YkmXJdeAPU12F5wnzDBPAFZFhp51HxHbWYwyI4mmPbaKqmrzFUlaNyolo+k+EbdZgqT3d0m/jkgnNY/hyOG98ba08w3/AGlQsOR0QHmu9+JkSwwwmHLbG8wAjpgH+lcz4Zt47bXdBklG03tpIMEfebOa9uMbI8Go7yuZWvaQNN117iOMRw3UWGHauSu9MiN7NZyRNt2jZx3Ne0a5p9veaOyXHLLlAwHTBriDp7NqShgNwXaSe47UGZ4x4s8KXGnySFYyFHIGK4mRGjYhhhhX0zf2JmSW3vIApYbd/UN6fjXjnxC8MzWU63KxBIW+Ube5q4yE0cW+Cc+o5qNjV1bRyQHIUepFXrHRPODN5oG3rVpkcrMRWycVIRg1oTaVIWPlSBjnGDVC5int38uaMo3vRcaVhpOBkVPYXDxTqwPJ4qsTkUA7SCO1Amz2rwhfLBptgsj4JcqW9u361u2khsvEF0U5SQByfTpXnvgu8e6s4Ldj/qjuYn3NekaUFnlvHYcyDarVNitzqlfe5x90pnNSLxx6Vl6fcMscXmMBt+Q+9axTHSoaE0KuacTTc4GKAOaNhC5pCc0PwM0wHNIB1KKZn3py5pgSD3pajNAbFNSAfSEim7qSk2BIp5opgoo1Ap/Z3H8NHkv6UNO/96mSSEkc1kakV4biCMNAiSMTggnFW4tpUbyAcc1VZuRzSBj60xF140znfVPVJDBp8ssTEsBSluOtVtUdTp0q5xmqQM2fhQrtMJpAGLnOa9VI9K8y+F8ZWCHAJHHOPevTjWqRm0MYUmD6ilY0wk+lMQ7aT0rnNT8QXtjcTRQpHhR1xXRqTmuK8Qrm7uG/2apCZz2s67fa4Y47kLtiJwRWdLEApIFLYqfNk7DNTyr8hoER2/3PetXT/uGs63X5a0rEYQ/SiwEuaVTTDQKTGWV7VIDioozxT2NIAJqrdkhkkUDCNk5qdjxUVwAYSPUYqZq6NabtI6WyuTJEuM4IBq1GIjueRuAOAawPD98JbMA8OvBFaHm5Jya4Op7EJaEV4szTkpbEr2OetcF8StFl1bSZUWyYyryuBkmvSo8Ouf60PbxufmXNX0N07ny7aWcot1gni8u5Tgo/BFW7T7fZyrlSy/pXvPiDwdp2rrukhCSdnXgiuUn8Ly6c2y5i8yIdHAzxXPNNbHdQquPU4+z1OPdtntiAO4rbsJ7eXARGGT3rbi0KxmA/drtPfFXIPD0KuBFgGsnKR6Kxk0rXHaZBG5XcqlfQjr710lpGsaqvas+y0yWHOXz9K0kQgDjpSuzjrV5TZd8xe1ITnrmoE3njaasAcDPWoZzvUryjJzmmBT1qw6ikUDvUiY1AQRips4pMDNMklReCetJmbY8SYpJXJBBIHGarTXCoOGBPes+7vJpW2IvHrTJuWby9CLtibcSO1UFWSZsyD9aW3hI5IJ9c1ftohvyy/SgRHbw8ZYcCrMaAnJFSlG9KZQguKaOgzgH60uKUjPFNsNzO1XasZlY8oM4ra8CaWYdKm1e5wJ7heDjoOwrIu4zdXsGnxjLSHL47KK9CtYEOmxxwqDEq4X3xXdhaKerOHFVWo8pwXxChmk8LyzwgiSKI8Ecv6/pWDp8UjeHdCv8AgS6ZIr5PeNsA/wA67TWdl6L3T2BDshVfbiuC8FTlrOfQ9TIE0IeAr/eXPFeg1Y809CMEMn2iNlHlyr5q+gyOtcPqtmI9eihkk/dSAlXHVG+npWl4V1dbUf2fqzs3knytxPLLnir3i7R5DDDcWeZIQ3mBCuGGPQ1AjDc/YrzOpxLJbMdhZeg461y/jyHTr3SHttPiFwpbKoBueNq7y2fTtdtZisLCTAiMLn5lOOeO9ZkHhXXNFEAsPs0okYmVWX5wDQNHgx8PLfXfl3jra7OORwa2NR0fTNOsvKeBhORkP6ivRbrRpxDffb7RUw5dGIB2+lYdxp9vc3ButQvlKlQXbGF+nNUmM8s1C0hj2kQMGP3cGsjU7G9uQEMBcKPkPU16Zq/iDwvp8hj2RTsvG8fMMe1Y9h4jv9Qkay8LaGGLtgyMm4j6en0qkxM8uu7S4tmImhZOfSoBzXvemfCzxRr2Z9faNd3IDACrEn7PKk7l1oJnoAowD+dVcix474U1d9MlkV1DRSqFPqPevbdK50KCeDEmVVlZf4vXNY198B54FCxa9Fu/2krU0rwf4q0G1+yBY9Rt9u0bG2kD6VLBmvBsuIUiQ/vCxf6GtyNyY134DY5wa53RbPXY7g7tInjUKVGa3IrPVfJG+ylVgfTtWYmiYn3pVNNFpfHhraTp6VHh1O1kdSOxBFOwWJmptNyfelBosFgzzTlppHNOFITQ7tQaQ0lAC5pKSlHSiwDhRSCilcCiUYGmsATVkiomWpNCvLuJG04oQHbT3FNh5U/WgBSPlqjra7tNnUkqCvUVo4qlreRps3+7inHcGaPww06+t0iktdTeaMkHY4zivXVdiMN97HPpXmXwnJ8iAe1enOMHrWyJG5z1pD1pcc0hpkCj1rj/ABBGSblu2DXX5rmNeAUXC9sUyWcRaEGMAHmpZvu0Rqqg4AznrTpOVOaYEcfEYrRsf9WfpWaDhBir9if3Z+lMCRjzQDSGgUhliI09qiQ4NPJHc1L0ATOelIwytPiieRwFBx3qSdEtlDyyBQTgZ9alyVi4mYTJaStLFny2PzCtWzvFdV2nPGabBJbXKTAKCqnafyrGillsbwwSLiMnMb9ePSuKUdTvoVLqzOwspwR04q+rKxxXPWdyMblP4VsWrh/n5BFI64yNMIMDntTZbeKRSrqCD6jNOQ7hnNPNK50Qlqczqfh9HkMlrJ5TdQO1ZyPcadL5V4hZezLXYuuTUFxbRzRsjxBwRyDUOJ2xkZFrdwXABVhj1q0oQgHNZF54eura4M2nTFFI5jbpVYX1/ZuEubeQqOrKuaxlEtxW50yYoNY8Gs2rfxFcdjxVgaxZdDMmf96s2iLF1+lNWqbapaHpKD9Bmq15rMUCMY45ZMDjahpcrMpM055NnArMvbxF4BBb0rz3XPHl89/9hFm9oAf4+pHqK0NNuWlkVt5LEZzUyutGCVzoTI88nU1es4wGzjtVKy5BPeta0wY+mKaM5IljjyM44qxEnOabHxxUqj1p2M2Ix7VFhQpPenycd6iPNKwIUE96c7Kq5ZiABnpTRWdq80k08Vjbk+bKdvHUDvVQjzMV+XU2Ph5A95d3upyqDnMUWO3vXZ6MS2nIDjhiP1ql4OsE07S1t8APkswrT0+JLe0ELcvuJ9xmvZpQtE8bEz55MyW06OG4uLrBMjjivPvE+iLBrL38COhkIZnBx81etXKx7ctIq/Wua8SRCa2aK1hM8nYqOBWjRinoefeJY7Wawivcp9qUfNg4WQeh96h0rxZfpG9tprG/6furg4Mf0bvTLvwx4hlldmChJGy8JOAfp6Vz91pVxbzyR/Y9QtnRgCqJuH1z6VLQ7nXNf6IrLfLNeaXq5B3s0RKMf8Kg1L4jCysRJPCLt0IUywcdPb1rjdTfXLaylC3V5J8px5tvwPbNYuh+H9S1K0a6mvnIHLRImAM/WpsPQ1PFvxKklt3a00xoPO++87YB/CvOL278T+JQVQPszgLGhVSK9BTwVC8yGSKW4kOMCTkCu90Lw2tlEifZt8n+yucUXEebfD/4QeeovdfkYg4KwqeCPc17DoukaVoMKRWVlDEgXB2LzV22s71j5aR7FHbvWnFpxRQZzhvSqRL3Kc13O67bdWcAcFqzZY7pQfMaUpnoG4Fa9/eRQK0MQBkHX0rIdrm4YBjgZ78Cm3YY0ysPlVsHFEPmv829nI756VPHprSOFMgYHsBXQWfhyKZQ9wzL8uPlOKzux2Kmm2VxOq/eB6n6VvWOjYiMu8bxnAbvWDJ9ltbpbXTnuXl7yKxKr7GtyyvplkaN5Y5GRQSGqkwsSC3bYI3iUSEdAKzrmyt5WHnQqG6ZxVnUNZRpFRreSNh0cd6nheK6i3pkeuRQxHLan4bhuAXtJAkgHQ9DXL6hp+oWLfv4CB6gZFemm0+bIY1FLGpUo6Aj0IqQPKy+R94VKpOMHtXZap4btLlWaEmKU+nSuUv7C5sLgxXK4I6HsRSJsQ5o70mRjINBNUkFhATkjtQCaKQVZI4E5ooFFKwxtMYVKaY3WsjQryr8uKZEuEIqeQZxUY4oAXp2qjrZzp0w9Vq6W9xVDXv+QXOfaqiDOj+Ev/LJfQYr0+TFeXfCY5MR/wBmvUG5yK1IGUHmg8UEjFMVgxXJeI5eZxjk8V1o5rivFLENMAD25pkM52MfLTZuE2nvUi8REjvUUw5FMRCNijBzV+z2mLAz0rOcc1esz0/3abAmZsDpQrUp5FAHNQyh6k1esrdZcO5+UdjVW0heeZY0BJJx0rZuoUjgMabx5ZwcVMpFpCJcQ8pGoBXrWfq8pMMkcyK8bKQBjr9KiiJLHnk1PcGytovNlfO0ZJIzWLZaMXw9m0spYpEkAaUkM33iKu3Kie3IBBGOPY1Wur+8ukZbG0zCB99iefoKpaVa6xKn2hQyysceW33dvrUWuaRdi9pd0UlMbcEdK6ayuS0fr75rBfRpVjacy4lP5ZqTSrrcSOmPlI96xaOqnI6qCdsgetWlkOcVhRyYcEk4rRglBcYORSOqMjSjUkZxTyvHTFFr82KsbPar6GyqMpvGHGDVV7U7uQD9a1dntTWQDtWTWpspMynsYJDue2jJ9cVXbQ9OaQP9kjDeuK2QpzyKXZ19qOVEykygmn2yqAIo8D/ZpstpFghUUfhWigBGScClKqfQ1oo2OeU3c8+8YeEbfVrJiEC3KE+XIF5HoK47QYZ7eU21x/rom2vXtVzAD93rXB+M9OWzvYr1cbZjsc+lZV4XVy6VV3sxNP6HNbNuNqCufsZVwPeti1myQrHjFciNZMvqfShpHHem9hQMYp3M2w3k9aC2DTd3FRSyKqkscAUwUh17cJCh55xVXwdvfUV1q7zs3FIxjlqwtcuZ7iVba0y0krBRjnivT/A3h8W0MM98qlkjBVCflBx1rswtJuXkc2Kq8sbI0LG4miilaK3kknk+ZQRwoq3ZJqLN5soVHYfMa0FC5yAp91p3Ga9RJJHjNsotYI7lp2aRvQ9Kc0KIu1QAB6VcOKjfDA5oJTZj6lapNA2FG4cisuKKL+3Njkqk8IfA7EVelv5LK/FrcAZY4DdiDWfqVvs1aweNssHK9eq0mi0zSurGyKICFb13DIIrF8S29la6PdNZ2SR4TI2pjmugutQtobMuoRn37EQ9zVPxSd+hJBPgSSY3bahoaZwXhy1lFutxc9Sucmul0mcG42Aqg9T1qnKIo4Vjj4XHFRIU3ABsZrOxaOiubvyoikCgvn7w61nzSTMczuWcjimWxZQGQhm9xVS/nlSQkHPr9ataEtaj3Fuqkt160yxt5r+5xEMICM5qOwtp7+ZQASufmNdrZW0GlWocj94egqGykiG0s7azhAbBbvx1pmoSvPGsTyiOP+6DgmoL93nJeWYopP8AD1rntWsoJwYYmnaZ2whL9PekITVNWtDqkei2koij4eV1OOPT61WtLo3Gu3Vzbq5tggiQdmI70f8ACO2cNyJDywTDNn5mPrXQaTp4baqgJEvRQO1CY7D9Hhk+/cwypE3AOMgGunW2hNmrwsGHtTLGOOHMTH5WOfapZrYR/vIiRzyo6VqlcViq0LAcEVXkiGDnmtFv/wBdVpVy31qZIZQeEdqo6tp8d9ZtC6bmH3T3BrYaMionXHGDUknk9zC1tO8DjDocEVCTXVeO9MPmLfxDjo+B1NcmelWJpi5oU0dqYKVybEqnmimA0UXYElNanU1qzNBj9qiNSv2qFjQAVR1//kFTfSrv41Q8QNjSpfemgZ0fwmx+6/3a9OINeZ/CcYEX+7XpjGtkyLiE8U2gmkzTJuOHf6Vxfij/AJb/AFrtU5BFcX4o4eYEd6Ymc/wIMVDNyufepm/1FV5D8lNEELE1dsv9Xz6VQPWrtkTtx7UxlodKlsrWa8u0gjU/McZ9KrxZYFRySeK67w3bNCiDoTyzGspuxcUS2sdppiFUKtKg5yO9Zmn6oklmxfAknmfavfrUNzqNsdRuLdp1Do3zBjjNcvo97bWeo6ncysSRMVhReSAfQVkzRROoktYvM3kEbuuOBmie3s5LuGEqCQMtu5HtVixuHvrMSNEUGccjk1lXdhLbXct6JnIlwCpP3cdKRVi1bTW9pqflcKsgzHxwpq219CFyD09q5jVGbEc8hOYnBP8AKptQvbayg82UhFJ+VQeW+lJlI0LzUZH4RQKyDIbe9ecfd3DcPT3qaJzLEJvLMYYZANV2UyTSKRnIrGbLjJo3ILhJcFCTxWnp7ZkO48YrlfDkpeZomGCldTbRMW+UHFZXO+CujdtZ0XAyT6VpW2G68jFYkSFSigdK27PKgZFO5u0icRJ1xTHiUcipd3+zUUhcg7cD60XuTdkTDmmFSaeGY/eXFKnNO5LbIJEwhqFSwc8fL2q44GD65qrcsFINNSFJXEkGRXMeOlUaGzMoO2RcHHvXRPKGHHBrhfihrUFtDb6WJFMsr7nHdQKVSXujpr3jItBl8BiBW3aEDGT0FcxY3O/DDr3rYhuH25rgudc9jdEjAAcU7zRjng1mx3AKjPWlM4XkimZNXLT3CjIUgmsnV73yoiCenX2ps12AWII4rndVupbuZbaJSzyuFGOTTSuJaas3fAjPcavNdIN7qNsYI6Dua9f01bu/hjZ8w2u37o71zHgTw+ulQ+TIP3xgLScciuu0m4ngsoI7lQYuiuBjH1r2MOrRPFxNRzkacaBFCKMKBwKVgQeaARwQcj1pHJrpRzaiMeeKiljWVOJGU9ippxJBrOmuTp8w83iB2PzHsTTAh1bRo7qCUvcTFgMoc/xVmWUpmW2Dg/arUt5mR0wODXSwzw3I/cur/Q9KzNURYrz7VGAHZCm3HX3pMaMbT7O+t8ahciKRSSYgx7k+lQ6+LrdGtxMCX52qOgre0izkcxy3jElB8kZ6KKwvEtyP7VZAv3RipZokZwhCrgkkds062hjJJYdKfMP3akdKfEqxoGznPasr6jRJcXAjVgoAwKzdst3ceQnOevNTXzAsPcitfwzprO+4gKScZ9qLgamiwQ6ZZkuVaQDtUF7ctIfMmIz/AAip9ceOJRbQkccNWHcys/DMSB0qWxiTTtITzxUIOH80ffHFAI9KntIPPfJ4UdancaRNp8BmfzJjxW7mGG3MkhEaqPl96qQRpEgUcAfrU0Fq9wPOuxmND+7j/qapIbIbS+1G4dlgt1jTsZR1+grTU3NsBJeXcargZGOtUmuCl7E7ZCg8irEkH2++Es/MCEbB/eq+axBZEqMSc598YzQNkjgZ5pmoRiKUBBhCOKgjU53BiCKV7gWnj+btiq8y5NWIst1P40jgZoAyNRgS4tpLdxndXlWpWstpeSQscYY4r2KaMHJxzXD+P7BVC3iDHY0Es5AE460uKaOlKG56UEjsUUoIxRQmIkIpjVIelMYVBqQyNULGppAPWomFADCT61n+IT/xKZT6VoEVn+IsDSpBTQWOs+FPHlj/AGK9IPrXm/wq6x/7tejt0rUxGMaAeKRqQZqhkqHDD61xfixsyS/79dkScZxXE+J/9c3+/TJZiOf3JqtJjbjNWH/1RqrJ1FUSRfxVatmIIqtjmrNupzx1pNlGpo8LSXyEfdXJIxXW2d1awwGZ3Cv0CdzWToNubazluGwJiuVB9Klmjkmj8xsZ6jFYzkawRkXdn9u1GVSIkjkOWYrk/hVWPSItO1Ca3h+R2XKynkk1uNbuqhhnI54pt2RJLDJt+YgjPesmzWxV0O9mUPbXcZEijIfsw9frVbWdatJkNvDKZHjYMxC8AA1YgYLONw4FWNUsoZLSXyYo185CFwvQ9RQgZUvLSG9svOgIYOmDz7Vw/k3kGomaWRbh1OyLzRlQa7Pw6sq6cEywAJDqf72eaoeIo7fT5Eu5U/cyna2BwD60MSZUS41eOLN1ZI277uw8VLp7yNOTMoQntmpI72ykVfKnRuOAG5pshBkUqPYVjJaGkIuTLOhqBfykdSea7XTv9XyK5zQ7MLhyDk11drGAoHY96ysehHRFi3VWbLA4rRQhF3KDUUEYC8VM2ACQegoZSkMe6JOMD8qUPv6Cqp5arUQ4BzQK4u3qT6d6jhJAJYdamlbK4xULDApi3ZBcT7WOTis+eQFGdmwq9T6VLf5Ln868b+M3jl7ac+HdKmAkI3XEit90Ht9aCmzpvF3xEsdPBttIIu7kHaX/AIQa8rvLu8vL97+7nMk7kknPb0rC0m7TO1/XPJ5Jrdji3oGHAPNYVJvY2hHS5t6NeAbctgEV0drcq2CG/CuGtQYZcnkGtm0uioyDWGxq1c63zxTLm72xEjgAc81iJeZGS9Vbu6dx97ilzXCxa1C9HlkhsD2rpPhDon228k167jzDbg+UG6ZrhrW0udW1CHT7VS8khGQOw9a960fQrqz0mDT43WCPaFZE78ck124WjzSuzhxlbljyo1dJmSC2lkI864mY4APOO1W7e2nmhQXkgVF6Ip4qtD4eghO5bidW77TirSaRCRzPOfq9eqlbY8W+pcjxGoRTwOBzUV75j2+YG/ep8w9D7VCdHt8/6yb/AL6pJNN2qViu541+uasRYtZ1uLdZAOcYYehqO/tvtNsyMmccis25sdTtI99pd+azHIQj+dQPe6tbqXu4WGOjoNwpNgSTvZWsEcyxul2x2iND940umG4n1a4N3s/dIAq/3c1nW6i5ZNSa/Q3AbmM8bB9K07HSVdZZ3neWWQ7s56jFK40aU91bpG5X52Axwa4F2NxqErHkkmuj1C/js7aW1EAAeMgsOqH0NczpylV87k59e9RKRoi7gFQh7U2ZgkYxjimMTtLVEzGXEYHJOKiwybTbdry8EhGUT9TXWPcQ6XabAB5zjhc5qlotstrB5jAYQbiapag7lGupyDJIfkA/hWk2BBeXDs7FiN5PJqqDxiomcs2SetOU5PrWTd2WkPRS7hF6mtizi8nbEBkn71VLCAhfO79AK27aIoquwwTVIGia0twEBmyR6VFdyMg2q3yZp1xcZ+Udaozvn5R3FNuwmMuGVyMHIrS0q9jjiZZRuOOKxZVMa5702KRnkUDn3pJ3EzqbpopLLcCAc5AqnA+7A4/OrWn2atBuYtt7inRxWsbAxjIPStEIkChVAFRSJgE5zzUzAVHJytAEBANYPiy1+1abNCAM7dy/hXQEVSvIi+PQ8GgR40flJBOcGkqzrMBttVuYMY2ucVUGaCWPBopAD7UUhWLhqN6exqNzUmhDJ1ppxiiTJbOeKbQAnesrxIf+JdJWo3esnxMf+JacetVELnZ/Cscx/wC5Xoprzv4T8iP/AHa9EetTEjNLSGgnApjFzwa4jxUwUu+OjV2pP8q4bxe3ySj3pkmQTmHPrVduasYxbr7rVdjjk07ksbjmtnwrYteamMj90gyTWKQXOF613mhQJo/htXcn7ROd2D1A7VM3oWkV9Ql8++yAsYjGxMdxURinZyy3DD0U8AUrks5ZgMnk1ZgBIB25Brnbuax0H2sTxqfNcsT2B6VVvspeWxPKklQtaUQ2kk8is/W4UcW7vkKsvUHkZoLTKdygWUgjA7n0qfSb2HUrdlgO5UbYG9WFZfiKHUbaELIzT2THEjKPnC1f0E28EMKWoVYv9nuPX60tiiSNUjLKMcnJ+tOubeK4tZIp1DRMpBFWNSgRJt6cZqqXyEjbOAwJx3FS2JHIHQooYiJYtxGSrDgj8aueHbRjNtaRpEj+7uOSK6jV7dZbBpCQCicHHasfwrb4yzHhjkY9KxkzoobnQWsYjjAArYsh8grMUcgVq2g/dj61J1GpAvy0k3yripLdf3f4VFNx70CuQDrVmMfKKr4NS+YVwB6UDHt61FM4CkntTZJCpwKr3U2RgnNJsZz/AI31uDQ9CvNSmOBHESgPcngD86+Rmv59Q1Ka/nlLyTyszMfT0r3n9pA3k3hi1jt0byPO/esO4zwK8Jht8AbVAApvRBH3nYswuY5VYdAa7fSZxcW4O4HA6VxaRsVztzWv4YuWil8pj+BrlkzqjojqfL75oU1IvIBHOailUgelQ9SyQuAOTVOe5fDMCdoGcUkjMAcGpdAs59a1e20+FCxd/mx6UQhdhKSirs9c+BOgKLBtcuIyZpTiPcOiev5161GsafNu3H6VjeHrRNP0qC0jGAiYxWmhyK9uhHkifPYmpzyuicsWNSIcCq2eQc9KfvBNbHOWDUb8H1oU9MmmSHmmgEhLKdoPXvVTULtYI9ijfI33V7k/4UXcsqkJEgJPc1Wt7LyXaaWUyyt3PYegoYFQaTbzW8hmQLLLyxXgg02yi1SwjPlXBlRBna/GfxrZiT+IisjXpLyUrZxERrK20MOuO9JjRy1/ez38EsksYRrmchQDxtFTKBGioOwxUupW1vaziCEkpCuOf73eqpkOcdayaNETK6hSD3qXSkVrgysvQ/LVEkvMqqeTW/pNuoeND25pDubFtbkafKhO4PxXM6vN5l06qfkQ7VH0rqNVmFtYOQQgVeK4cSGSQtnOec1EykKeT6VPBEz8qaYqE1q6ZAGxxwOp9fapSKJtGSRgTOm18YUH7prTmciNVGBioZHCj+g7VDNJlKZLYM3PWondFUu7BVHU1BHLmWSMDAQZJrHNxJqV+zI221hOF/2z/wDWoGaJmNyR5ecH17VsaNp4LBjwO+e9U9Lt/MbhetdHAghj29+9NITJ55xGixBfvDAFQpGFjjx1A5p3ktK6yhh8hzzTxwK2SsiBp6Uwk5pxbJwKYetAXGsKguFymB17VYNV7oEDNJgeVeN4Gi198kZdQf0rExXR/EQ/8T5GxgGMVztJMhsFNFOA4opMCwxqKQ0rNUbHJqDQY1Np5ph60ANfoaxvE7Y08j3rZbpWJ4p/48T9RVR3EzufhKw2KT2WvQi3J9K89+EoHln/AHK79jxWpi9wLc0hOajLe9KD70yx/WuG8YdZgP71duSe1cP4wJ2OfVqZEjKZv9HX6VTmb3qw3+oX6VXdQzBcEk9AKCdzU8K2D3+qRjH7uM7m9PpXV69OssyxIAAgAA9MUmiWkekaGDuBuZhvx6exqhEzzSl35Y8ms5y0NoxJo1Jj3DlvepNLu4p3kgUhZI+qng06GIhcdO9UNUtbeVluAJLe4i6Sp0P1rI1tY3EAJwKr6ugNjJydyYYAeoqvZ3bsqCVkdlwNy8ZFS2jMZbx7hvkZsAt3FAkWIwk1qhbDCRc1lf2Z/Z7MYmxHIchR0FammCIRtH12n5fpVm4gMqlMZIFJllWWDzbFJg2So5rLnAUA9z0rZsEeJngc/KegrP1S3KMy+hyKhgM1K5UaESMFmOzFVtFiESoAMADmqeWuLpIQcqnzEds1s2ihcgc1lI7aUUlcu26Fn56VsWyhAOM1n2YO3pWrCCdvFSaFyLIjz7VA/XFTuSE4queTQSNPFIfWnMP5VHKdo4p2GiKRucmsvV5VgKyM4Vepq80nBJOABk+1eYeLvFCXmppHayCS3R2ibaepoUOZk1JqKO08T6daeJPBNzakqCy7os/xHt+tfMk1n9nmeBx86sVb65r6T+HUr3U+24G7avyp/CgxwK8c+KWknSvGt3EEKJK3mr/wLmniI2hoThJ80rM5i1gJXAWqrxvbXYmXgfxVsaagL81LqmnK0JYDPHNcDkeoomnotwJYR8wPFXpYlZTkVzug7ouCcelbn2h9hU8+9CYNFC4XYxyOK9Y+B/h1Le0k1iWMebMdsRIzhe5rzK0tZNR1OCyiHzSuAcelfSPh6xTTtKt7VBtEaAcV14am3K55+NqWjymihCLtHQdKcHJPSmUV6i0PIZKH5xipug6VXQFvnHQVIWO0YPNUQShm4GBj1pCRuOe3NIGAUbjyahY/OT3NNAKcFs4qOT75wKUtio2J3nFIC2v3R9KoTIovGnmVcop8sHr9auJJgcjNYfi+7EVrwdjv8oOenvQykjnZ5DLLI2QSWJqrLIsZALDPoKz2u59Ru/s2nybYlH764b7oPoKkASJRHFuJ6EtySfWsb6mqRqaQGmu95XAQV1OlRAkSemQPwrA0qJoYIwT8zHJrqdOQRwsZAFA5pXFYyfF1yWgCZGCcCuegGEHFWfE1z5moLGh+Ve1QQ8/KOvWpcr6FouW0XmMFHetmLEUXlgEc9u9UtMQrF5v97pVtmJGTQhMVpARg5qq824kA9Dgj0p0hIbg1lahujm821mVZT1RjwaGNEV1dTFb1Y+GYhAR1+tX9IsNsUVupHyrg4PfvVC0iJDMxwc5fH9K6fR7aRIS6Wu3PQuf6UBI1dPtUtYQf4u1TZ3EFnUevNUXivpzteVUH+zVWO2ik1F0aSVljXJAPBNXEg6dHtYI9rSoM981UkdCx8tgw9QafaWlq9uG8oHHqc0lzGkYUIgXPpWoiHpS5FJjINOUfLzSsAxyD0qrdMwCr6mrRHHI5qpfEBVPoamwHm3xEX/icp/uCuaHWum+IwZdThlxwyECuYB5oSJdh4opAeKKp2JHOeaaDTWY0isawNSQ0xqCaY54oARulYfiv/jxP1FbJY1i+KTmxwemRVREzufhOf3bf7ld8TxXA/CoYtye+3Fd5nitTITNGabmimMduri/FoJhkI7Guy7H6Vx3ifiNzjPzVQjntPuUvLMMOCh2sK2vDFi9xqBmURssK5+YdfasLSYVS3mZQfmbpXX+BVJlmbHHApSaSBI1NXIiIkRQA4/KsqDIG7B4PStrXI/M3EducVmWmSzoFBZl4z61zydzdaF9iSqyKp5ABFTQhRLtYAq2CcjvUFghEeG+9VgKQ+AefWkO1yleWzzXXl28KxAHlzxUZS9lvfs0USmNfvSv0P0rXyxxnFLz1xQOxUvImgaKROQBhsVLDO4Zc9BVoxrIhQ9DVaOLaXiJyRSYyaZR5qSAjdjJ96XUbVZ7PzP4gtQwlmynBYdPaotf1A2uhykDEjDy09yaiXcIq7sc3pce6aSfpk4FblrGM5GazdNiK2qDPbNbFrG2wHNYS3PRirRNG0T5BWlDwBVG0Rio5rQTjFTcRIxBTmoDUpPFRNRcBrHHNQyHPFSSscbaglYDJJAAGcmqTuwvYx/ENz5EBjViGfjg15j4o0hheWf2CJEaaTMgHA9SfrXa6rc/a9QaTI2gYA7VTljJlgcDJjfv+tdEVZHFVmm9CPw3dnTrPzI2H2iebauTT/ix4KbVNGTWrKU3F7CmZVDZ3D0ArkJFzr893cxXEtlFIf9WxHlN9K9c8D32kXFltt5fNRhtb5i2D75qpRUo2M4S5Xc+bLU7M4zkHkHtWnHKskQB9Oa6H4u+FD4b8StcQqRZXg3qwHyqTXIxSbBntXl1qfJKx71KopxTJRbFJy6n5atJKNvzdRVUXA7ihZC7hY1yzHAFRHVpGraSbPRvg7pDXeszanIF8qIBEJ9e9e1llAwCCRxXJ/DnSxpnhy3hZBvZd7E9d1dKSMnnvXsUIcp87iJ80yVWJfnpTxyCfwHvUSng+1SqjIig9c5roRjImiGFx60H5TQv3xz2zTjh8tngdcUzNDGYtj0FNJ5FJISCMCkTn5u4oAbIcZY9AOlIg3E4pZPmyPfmlhGO3WgB33Rz6V5t8R74Sa5babNMILfG+SUt056Zr0W6cJHk4zXkXiqNb7xBLdalcMbMPtjRCBtx3NJs0iWo9R0WzhEUV7BGiDgZ61Jod3batdbrVxIqHLHGOlU5tP0tEMggil3cqxHat3w3FHDp5kiiSIueQFxxWJZrpwy9ua6CMkafISeSOawbVTNKoGBzWnqsn2axA3YJU0r2EtWcZfTNcatK38IO0VqaXaiRlBb7xyc+lc/pO64uSCfmLbvwrsLKMRRLlfnbv6Cs46ssuoiEYjG1FGMVDvAJHpS3LmMgJ3qrPMWO4gKcdM1YuolxMAeOtZV3FHeZjkyG7FTyKkuJGOexzV/RbBpZQ3fvmhsZoeH9KVI0llGVA+UHqT71tBvmxuoUCOJUAxgYpAgeI5OCeKEgKmq6itpD8g3ykYUDtUGiP5RMF0MXE/wC83evtVqK0giZm273Y5LNzn/CoNXjbYlzD/rITn8KsTNuwdmidCcbWxipL1SbbzB1WqNhcrvWYf6uQc5rTzvjZSOCKtMhsowneN1SGo4PlyMdKeeTVCTEcZzWdf8jA61olsVnaiPnB6GkM4H4kIC9m/fkVyArtfiUo+x2rdD5hH6VxINTzCaHk4HFFITRU3JsMc01WpJW4245pq9Kg0JhyKbJwtC0k3KUARkisTxa2LFf95f51r7hWJ4sYG1UY/iFXFCZ6J8LB/o7Y9K7djxXC/Ck/6Ief4a7cnitTF7iE80gOaaxzSA0FEx6E+1cf4o5hfBx81dcPun6Vx3ic/uX/AN6mSzKjAS1ULxxn612Xg6Dy9DVwMSFic+1cdAMwID34r0bQY1i06JQOCnWpnsVEivF3wnGc45rFg3Ry715KmuguwkTHHII/OsWVDDPns1YGyReUgEOvIPNTcMQw/GordMqE7r92p1GwDIz6igtC4zUqDinDGzOABmmHPagLjkzupZ4gCJVGGHBpxG794vAA5FK0nyH5ScipYipNFs/fKeOp+lcx4muDdarHaj7kHJ/3q0dQ1ZrJLmKSIyJEuSQemegrm9NMtxIbh8kudxz71lUqJKx1UY2d2dBp6logB6Vr2ykAL6Vn6chVPwrUtRk5rHmudBoWg+WrnSqtqpxVsjipBjGNMNPYUxuAaCSKX734Vh+K7/7FpjbQC8uUTPTJrZdjnrzXC+LL1bt5dhyltIAff1q4x1JnJJGZolpNaQ7Jp2lJycnqM1qwoS2ccDms+2v7OYIIpVZ2ONuec/StVDtAOMMBXWee9zlbP7Tb61qV1bIrxOy7kPOR3xXZaHJb7Fns41iVjnCrtP41g2VqIRK2fneRmU/XtWtpPlvGHiV43jbbLH2HvTWgmdX4m0a08XeEpNOuMeYFzEccg9q+ZdSsrnS9SuNPu1KyQPsPHX3r6R0i+aGfaD8pPSuY+N3g5dUsE8SaZCDcRLiaNByw9awrUeeNzrwtZwlZ7Hh/mAV0Xw/sRqfii1gA3ImHf2rkJXYHDBgc8ivVfgbZfuZ9TlUnc+xGx+dcdGk3PU9PEz5abZ7JpymOMk/dAAqRT0z0JqsGdl2A8Vbgj3yJGe9evBWPnndu5NGjcY5BqcNuBOMdqBHsJIPC/wA6AP3JHetRCwfOWbHtU7gBflGPWmWalTtI5NSOQW4oJK85IQNnnOPwqIg5Gw4VjzU86EkY5x2qvOGWQKRgYwKAHb+nH36njXAxVdHWSdVPCoKtFlzwc0MEYvi25W00qSYnnov1rzZ0hnUieFHVvvDHWp/jXd3t08drptxJCLZ90xXrz0rkfD8slxGFubi7S4QfOC3De9ZSZrFG09mLd/8AR3KRMeEJ6H1FdbYCSO1jEknmNt64xXL2uoWdvfKk0csxVeBjJzXUwzCaASCJ4wR91hgiouM2dGUFi7HGKr+LLojT3wCdoPerGmMPs2B96sLxRMZIvIZSfMOwAUtwRB4VtXa3RmB3OevtXWNhWX0QYrN0uAW1sEQYVQKt+YCmeSKErFjbojzN2eAKy76YM3y9h1q3dXCY5BFYb3ImvY7WI7mY9uw96LFJWNCzja5l3PnanU+tdlpkKW1t5jD5m6Vk6FYbisRGAvLn1ralIeQKCAq9KdiJaD2O5Qx70x2O35OlNdwXwDxSE7Rk9zimiWwQOW5FTMq7ShOcjBpqUStjLE4HvRcZHlRtVRhAeBWxDIDGAO1Y8rEwnysFeua0NGfzLfA5xwapMmWgS4WcgdCaXHNPuiolAAyw5NR3BIXevHtVolMhJO7HFVNQXLCRGDr0OO1TrKHPziqN3DJaAtEcwscsM9KTKOQ+JqN/Z1u4GQsnNcLnFehfEgE6Gso5USCvOckuT2NQxXJc8UU1elFSGhBMec7h6UitUEzKTjdxSxOCcZ78UWKLasfWh2O0iogwVeTimPJlThu1FgE42ZyPzrD8Un/RE5/irRdiV696xPExP2eIc/6wVcWB6Z8Kv+PMn0Wu4foa4b4VcWb/AEruJT1rQwe5GTzQpphNAOaCrkxbCH6VxviiQLAxY4G6usYnafpXF+L9r2hXPBb160yWQWSlzHGvJPSvR9JOdMRfQYNcB4WAa9hHBO3Ar0OyiENuIx2JNRPYuBHeqWjDdx1FZ1ygeIHv2rc2eZFkfQismdQkhQrgDOKwNUJYnchbnI61a2FgOnIzVOxkMTEN0NaUK/u/U0yxkDAjy2PepZEwcYqvMpUbl6g1aicSxhvTigBiqcYycU7GAaeCB1qtrFyljZSXcjAJGm76+gpNjirs4rxzJDNrkVtDuDqmZsdDzU+mQBYxjsKxbJp768lvrn/WTNuyfTtXTWCEAZrhqO7PQS0NC3XC1o2SnJ461UiUkCtS0XCgjrUoovWyqBg8HFSP7VHF96lY1VyWIainbCZFPY8VWunwn4UXFYoancNFZyyDqF4x615xB58xvrd+Hc78fU13erSl4/J2cdzXGX0n2HWg+f8AWArtA6ntXTSWhyV5rY5+/tIprtkEgt5omGJU4KtjjPtXW6P9oFoizsZCuBvI+8ay7HRh/aFxa3BybiPdIe4PbH0q9ob3EDvY3mP3X3Wz1Ud62OYtrD58BjDFW3EbvQ0+xMvnB2AEi/JKB/F71W8OXn2uOclMbJ2QHt9avW0kTXk0Rx50JBPuKBGpGjDDDIJ6VuaTe+WPJmBdSMEHoRWbbOsiqzKMdquEHYrKBkNz9Kpdhve6POfjD8MWZZNe8PRb43+aW3HBHPaug8AadFp+gWdkowyx5lHox5Nd8uoWqQlJ2xGVx6/pXMXEQttVN1aODA/Lp0qeVLY0daco8rZrwnMiL0wPzq/BhW3n+His+2+crPGD5fr6e1aroptwFHLsKuLMXoTfejCgg7ucU5sfKvfvUUDMJC68r0qVFyxbritiB5+RCxOMDio1fkAnqKdcZ2j3qE8MD2AoQiwhBqC5IMhzztFSRuu3eWwKryEZLA5D9PagBqxkRmTp61HLdCCB2JwAMknsBU1wxUbRwpHNc141uWGiywwkI8oCc9eamTsVFHEarMLjX727J3wXC8AnPSqHkhJGYADClsj09KoahpOpTjcuoNFtGBin6HaapbyIl9qAuklJjVSOR/nFZNmmxqLIbd7SZ0ASQcOB9w+9dZCTLGhOcuMknv8A/WrmbEs1s1pOu5om24I9+DXR6fwsS9sHvUgbtsix227IFc5cfvdRLj5gjcA+tbkzYshn0rHsSPtTA9Scimho2YpDHD5Y5z1Jpsh2xnBApNwHDHBHFULuXllU0Fmfq9zcO32e2HzNwzHsK1PCuj+Uu9QGZiPmPU+tVtOtmubkrjCn71dvpNrFa25kYfKg7mgTY50FlCIF4kPU1CvzZ+bFRT3DXE7SMQc9PpSAFst6d6AauSn92xXP5VLGHfqox15qMmIxK4OXBoluNxATpjBppisThwp5P+FQXE28YOAPQVG3KkGoQVPTmk0MlQnbj+H0rV0DIlYdjWdbR78K3y+9bGmxrFKMHPvVRSImi1eIqqGCgHOM1SmOVOeav3oLIMDODWdNzn61oQkVJAGQru2Z/i9PeqP9pT2c4huoVljbjP8AeHqK0CidGUt7Vm6mIQrAq4UDo54/A0WGYvjaFLzw5M1u+9IsNgdq8xzXp11Osnh7UII2HKdh1ry8dBQ0Jj8mikoosiTKkkO7tT7dssc9ark0+L726sTUtkkc/wA6aTwaYW4ppbjigCJ2IOKxfETllhUEEb62pRkZFYGvYWSJQeN1UgvY9W+FYzZN9K7Sfg1xXwsOLJv92uyds9a2Ri0RNntQpNIzYNIGNICRj8h+lcP4qbESDPG6u0Zjsb6Vw3i05gX3amSXPCnF5G3YV6RaYmIO4bD2HavLdDkZFRwenWvRNIu0a0QqMAjrWc2aw0Lxja1meORjhjlaqXsW+MSL680W99Pf3ZWMxrbxHAdupPpU00qkvGu054I9KyNEZWNrcVq2bboweKoPtQiMjntirVsChA6Z7UFlmVFfg8VUWQ205jxlW6GroGRVa9i3x5HVTxQBYZwgGcDPQmuI8fXrXF1FpCPuyd8pU9h2rqbi9EGmzXM+1PIXdyeprzqylkvbqW/m/wBbOxbHoO1Y1ZJI6MPG7uaVig3qAvA/Suhs0G0HFZmmBCcbea2rdMCuQ7Gi5bx8CtG1BC9qpQLgDvWhbfcB9aBEq9aa5NOz1prGmBGxOKq3coAwTVp+RWTfEmbFOKuyJOyK86iUmua1OEQ6tBdMm9RIBjsM11SABW+lYWuxf6HJICcj5sfSu+EbI82buy3f2sQv/tMSjcVx8orK1zAgaRUBn+6g9atXep2+naDDeXsnysoPuxPYVFCr3MK3065d0JVccKKdhEGhWv2SzSIDG47j9atvaRNfC7XKynhiP4hT7PJt0PqKsMm1sYJpEmlpbqFZXAx29queZsgV2GHb7qnuKpWqoI9z/KiLuY1Qh1Nry/behCLxH7ik5DsaqQtK5ZyOfTtVSRWWVgvY+lWrebLbQaWKLfdEeopoBmm3z2blX+aJj8y9q6ON45rbzIM8DOPSuWZPLnUMOGPNWLa4nsZy0TNtb749qpCOntsmJRjkdatWvRuKz7S4ivvLNq2Dj5ga1EXauK0i7kcpBMM7j6VVdiE+tWrp1jjJPOeKpTZDKhHIHNWSNaQIFHPzcVImDKFzlQODVU8sSw4HSrFnHshZic7jkUALMrSE46CuJ8bOW1COEHKqASPeu1uZPs9s8h6KCSa83vJ2ur2a5Yk+Y2R9KykzWCKNwMRn1NUVLC5sxjgT8/lVyYlm9qWJEZ1JA4OQazNLE1zEqXKyqRljz71v2qL+6I64rBlO6RARgA9q3rXomKCCfUmItgAcVSsYsyGXOAnJNS6kSxXn6iooZMQsBxk1Qya7mMhyOPpVNQWlxyST2p7ZP0rR0W1BkEu3cCeM0guaug2BVc7cs3StLWrlVEdjDjj7x96sBksLJ5iOQMKPesK2MlzN5jjBJyaATLRj8tBkgnvTwH2YQjB65qO6KrKVyOlOVsxAZ6UmWKik8dh1p0kioQUXtUTTbW2Mwz7U0SK2Ap5zQBIdz53sOfSpoo1PvimRxnIJ5Bq/DEAuQMfhVJCGhFK4f7uOQais5Htr1URnlgY85H3atMAOp7VYs2VhsAGO/FVEiTLtzJ8mQQeKzZ5Fjj3ucDPJqxPGI8BSTnnmq82ChUgEEcg1oIZA0coLxsGHtzWZ4glsBsia2a7uHbCorng+9Ml0mYzF7CR7b+8Qcg1SgjvtLuWMpQFv+WpTNABqEEUFrc2ojAkNsXdQOF9BXkag7ASCK9flZGWaYtmZ0IJHRhivJbgASEA8BjgelInlGUUUUwsjCNPTvUG4mpVYbR61z2LJC1NDA5+lMc/IagWShAK7vggGsPWWPnQ5/v1rysf4ax9ZH7yE/wC1WkUTPY9c+GDf6Gf92uxZhg1xXwwJ+xt/u12DHitTMaxzSqcUwmlU0JAPc/IfpXEeKmxFFx1eu0cjYwx2rjPEEZnuIYTz8/AoBIs6fGqWYCjDN3q7pGoyWhlhcg5DYyalisAsIBBUgVjamhAZunOKxnuaWO903aljEoQAldxI7mros7d1zCNsx5J9a5DwbdyNbbHvJJVzja38JrqmYiUlSeg59TUDRBcho/mkJDL8oPrU1vJ50Y55U9asTx/aoYy2N4BBJ9KzIs29x5R4welFirmukibfmODTWkjI+8DmoiMgH1qC+nis7Ka6lOEiXd+IpN2RcVzM4/4iXgmmTSbd8bgJJQO1V9JtwqKCM7Rg1k2jtf30upTEk3D7lz2XtXQ2EYD5XNcE3dnpwjZGlYx7WyF59a1ouAARyaqWqEIB3rTto8MG6nvSQ3qSwIVWr8IAjHNV4x3qwG4phYcTTT0pC1Ix4oAjlOTWVc5acKO1aFy2FYj0rMtppDKUaAkZ++a2oxuzmrzsiUrttQ2OSaoauhNnICOi1sTxlkCpjg5rP1VPMtnC9SuK7mcBzkmmx3mlwSXYZwifKvVRV6YMmkgocFl2r/Kp9MQvpkSDoCQc1S1sTMkdtaHATnd6E1mIsWyLAkcTOAwGPc1pIpkkQkE+tc7o9vbLetHced/aKcMsjdR6jtWtr169jALWAf6RInzHP3R/jUsaKvijUdrCwtpPkXmRl7+1GiShgSP7mM1hQIxj+c5JOcn1rU8On52Q9agqxvLkKWAJxycdqlWQsA6HBHWmW7FGIxkHrUksJDB4jwRmtUS0K8yuwYryKZM4CNI33RyaVDvHTFUtclZIEtFPzSNz9KbELY3sttKJ4CQM12mk6vFqNoeiSgcjNcLCm2ML2ozJat58TsjDpzTg9QO5jDtOQ54X5vyps8oMyFuN3NUPDmtW98n2a4xHcbcZbo1WtWRopYj0ArVSRLRKyA4A/iqzs2YTtiooyCAwPGKuJGWiLHoBmhisc74tufI0qRe8h2CuEkxGo4rofG90sl+LdXBSL7w9WNc7cNlgPQYrGRokV5CDUfTpSScGlHzJms7lk1uzPNGnXmuitBsDE8VzunDN7GPU10IBWNgTnHWrRLIrtsy/eB+lRJUbnLHJxTo+SMUxFy0j8yTb2710+iW4dg7Ljb0rI0m2O4Aj5jXRTSf2fp7yLjpj86AKGu3JuHFtH9xGycdM0y3HlgZyCPSqtoS43scEnJqaeYRx7gfm6UFJEU0ytcu7nIHGKejyu+1NuyqtvEGDSSHlu1X7MFlCqpHuaChy2zBiXarNvCijG0HvmpUiQEEnLHrzxQmCS2OhxTURXJUQYqw8/wAuF6Y6VFGASOpHtUohlcYjjwDxuI5qkhNoiX5pQprQtYgrZAwKZZ2Ekcu+RgwxzV8bAMAVaRErPYglTewwelVpLSY5YKTV9WQOd3YZpFly55wPrTJ2M+O3m2FsFfaoGCsDHIA2eNp71sEr6imNDC/3gPwpjTOWvLVLWT5EzbyDGB/A1eP6xEsGq3Ua9BIa+gJ9NR1YKxwRwD614h4406fT/EVwsoOJDvU9j60gbMbNFNHXFFBFjn4RnvUoxjr0qqrlTwcU4PnvWBqOLHpmmnHpSE+9JuBOKLAMlPpWPrbbZICT/FWu/SsXxCf3luP9utIbkTZ658Mf+PMn1WuuY8ZrkPhocWOc/wAFdYx9a06khmgGm5HrTWPpQIfK37s4PauVvZMazZptUneetdJI3yH6Vx+sfNrVkmcb3IqXqI6Vb1Y5jHdyKxb5VdTwD6Vg6lMv9nLOx27pWUZHXFb2s2UB07/R4VSSP51IHU1yMttd6hfWt3c3EJtYwzhACNrDsRWLRrEg8I3vk6pchbvfuIcrnG32r1O0uEliRgScqCTXlX9mJdWsxtod895IG81flEYzzjFdfoiyWFrEjyu6g7SWPpQimdnbyMGXk4rJiJv9SluVZtiSCHj+dWLa4BhLqd3BPH0pdNxbRmbBMUmGfA6H0oEWo2MfyOSR0zXH/EHV45400e0mDHeDKV649K6id/M1KGGKXKSDn29K89l0l7bWLgSglhKzFj1PNY4jSJ04dXkT6dbhI40AwqDAroLWLldtZ9uhZguK3bBEDAZGQOlcKPSehdt4yCMirygjpVeDmQYzirqAY6VTM0PhztOamzUacDFOJ70IsCwprkkUjEUMwAyaZJTvZFSN9zdqisWWRQyEMB6Uy9eMMpcgK7YBNFhGtvLKwOyM5612UNjhxTLacys3OKpakrBXOMfITVkMCoGeDVeQ7mdGJKkYya6GcSZl6HNusmVhgrIc1YgWGezunSQM+4AgVz17b3NykkFqWDNNyVOMDvW5a2cNpZNcF2ijGPLUHlyKlosn1AQRwx3d0i+eF/dAcPnFc5IXlzLK25n5JH8qt3m+7v8A7RM7ZwNo9KesMYGNtS0UijFbkJkcjrRp9z9nuw2MAnmr74VSduR0xVGaNCvZTWbRR09oyy49+a002KmNueMVzWmzhFTLcAflW60w+zq6nORxVpksRowG3IQvPftXN299DqOpTqk6l4XMbDqc+tS+Ptbm0vQRPbgebMdi57cGvFtC1u70vVF1BXLF5CZgT1yazqVeXQ3p0HNNnuDYTo3FRTTCSMpnkVXt7mK8to54SdrLn86QDB4pqRk49BuXXJVip6gg8iuh8P8AiBL2FbG/Y+b0VyetYDAnI744rNt9wmOM5FaJkWseqWqNHIkRORjg+tX9Qu4rDT5ZZW2qiEknpXDaL4imtvLjul8xBxu7gVL4u1uLUbVLW33GJmy5PpV3FY5FLi41bUZNQnVo4i5KIDU9xy5I71ZVQAAAAB0xUEqnd04qJGiKMgOeaarY4qedW5+U4qhM3zYzWNhmlpWDeZHYcVvSOPI4POOa5/QCWnJ9FrblOLdieOK1iyZFNiWfPvWjp8StJkjhazI8tgjnFb+lwl3RT36mquSbeiRMS0jjCgdTVXxDdvPdLbREeXH9761oajKLCzLbh935QO5rnbYFg00zfOxzQFySPeHHJ2DrU98VKoqjOR26VGZRJ8qD6060tJZHBIOBQO5NbQxIgaRyTjoTxVyxnS5VvIIKqcHHSnx2nIUorLjBzR4d0prK9mhbHlSHeMdBVKIXLn2aQBQT19BV21sQI8MuSeatIkYYZPI96lMkanBYVolYl6jILWNDnGKsoATgY4qubhAOtPSYY3AgGi5DRPuBU461QmmCNtLYonuwiHYwJFZk0hlbLGi41oWhJI6vJu9sZqC6d40QpuOeTUkOAmO1RzvgruHGcUXCzEWeZiCGIFWoroBgrk/WqFtMJ1d0+6CVH+NS7Swp3GlY2UfPIORXn/xg0h57KLVEYkxthgew9a6yAzLwZCFFR60Eu9Int5hkOpWgTPBMgZxRRcjyriSJgQUYjp70UCOTYkHmnK1VxISeakDcVjY0ZIWpA3NNJpAeaBDzgjk1heIGO+3HffW2TxWB4ib/AEm2H+1VRRMj1/4ZuW0w57DFdYzZrjvhg3/EsauuNaokXNITTc0tDENl/wBW2fSuL8QME1OycHlZM12cx/dNXC+Im/4mlsP9ugDt7KaZ4suM7vuooySP6Vm6ppUZm8+13Jv/ANbGRhR/9etDTblba1ZmHLIVB9OKhkuH/stIwrM75+dxgLz1rGW5omVdMNpFbrF5kabGIOWxTri+tbu4SK3mQQrxuLD5jXN2uk6frN2TLFPJJLESrRsQNwODXT+HfAyWqob0Aqv3MghhUFFzTrl4d0TdMHmtuxmU6dHKTxtwKgm0S3WFvLmdeMDJqmmViiso23RxEc+ppoYuniZbtJABkvlRj/OKg8QIjapJOpzv5I9DWxawsFO1sPx2qx4k0yKbSPtlsu2eMfPWdVXia4edpHNWK/vgcZrYt4sHf68VSsYgB5hrTta4banot3L0CbcAVZUcVEi8VMvShgkKKRjxS01hmgoaT70yVvk6ihuKikbahNMhmfcIlxLJbu2PlyoB79jS6W7vbGC4I85Dgkdx6057Frt1nt3C3EZyDngjuKknhf5GZNkqnnHpXoYZe6efXd2SupjUIeeOvrTSoMbH/ZNKxJGWOcDimlv3YAHWtpI5FozLso5bK4aaOMSK3UGrFyxupRIw2KvRMcVJzuAxSyLxmoZqin5Me44HSq7jDYIxir8KgFqhu1BbIpAUbjiH8apMC3GKvTpnA64qpEVadkB+dPvD2qGh3HWpY3TJkAdK2A7LCg3dKxbcE3nB5zWoAVTYx5oA5T4w3INlYRrwFV2I9c9K8qhi3Rls43DkV6b8X4Jn0yzukjYxodjtXmqtxXFX0Z6WH2PQfhpqLy2UmnysC8Ryme64rr8+9eSeCrmSDxTb+W3EgKspr1UuCeTxW1B3RzYhKMibI3iqlupEjEjqavWUJuJ07rn86L6HyLhlOADyBW6RzMrS8Fcd6eq7kGRTlj3AEg/Q1PGoyB0FUhEIGBgimuD2zVjCgkHOarTOdwA/GkykVJydrAk/jWbcKBzjnNac/wB+s2+qWikXfDoy8pxWzen/AEfFZPhr/VyE9zitK8ORsFESJ6MNNALjI7112hwIFMjjAHJrA0eFTs4PJra1m8FhpxjjGZXGFAqrEtlXVL5LvVVQMDEg6epqJFkmDMVwM+lVrC2aPy5ZRmR+SK1o380FEUKBxgUxpENnbEMc5Oa6G0tFjRYiR5jDIqrZQhJAjDcTT7kkTFyxGOmDVIbRcCxI2NwBHvUrTJGu1Oc1nxQxuN6sSx561YUYIB4zRewFlp9oBI61HM27GG6jtUVyRuVQenNIhxxRzMCSFS0gHOB1qdmJORnFJbodm4HBb1p0q7E6gn2p3EUXJ3HPrSxJvb2ps0SyqVcEjr1qayQIpxwg9aTYEz/LGWUcKKzdTn/4lssqnqpwa05OVIHQjB+lc9NufTbyzIAeMkj6Zq4oRb0lfJ02ME8kZOavQsSuajtbdfsUJZusYzU6qMYA6VdiWx4Pao7obraTPpmlY7QSTgCqcxlu0YRs0cI7jq5/wpWE2c9deGLe5fzHRcnk8UV0MLZjHqOKKLE3PllfpT1OKjDDsc05WqDUlLcdKYHFI54qMkZ60rATk1geIeb22X0Nbe7isLXiTqFvVRE0evfC9caW30rrSa5L4ZcaW30rq+cVdiLhmnZ4qPmjOOpoELOf3TH2rhtZt5bjXIwiEhTzXX3H2u4QpYQvK7fLnsKu6J4KSCVLzUrmSSXGSmcYoYFTTrRpmjeRW3AfImMj8a37zSG1LT2tJt0atwTjBA71owwOjeVaopHqR0q7DYXioGDqSfU5rNq5SMvS9NstItFt7dFjZeRx371ZnS5Kb2JYVbfTXMnm3ADsOgU1m6veyyS/ZogYwvBNQ9C0UtVuo0CxRfM7D5j/AEqLS7UkhmGOc063hG/O3cfetSwVQWO3DA8DtSGiMxtFMjKuV/iPpVywfzDJBLja6lcVX1W2llhElvcNE3TGOM1zlvqWqadcPb3cUdwrKWVgcEH/APXQxrcsrE0NxLC3G1yAPxrRgUACo5tjQW90kTo8i/vA46tU1v8AMBXDONmelTd0W07VJnFNXgCjNZtmyHE8dKY7HPHFKx7UxzzUjGsPeq1022Mkmp3OBVSdtzbevtVxRE3ZC6bJbAsVdsnrzxWm6i5gypBmjHH+0Kx7O4idTGmAV6r0NXbScxXIkGcV2QbWx5tTXUhaOQRru69DShwkojxnavWrd6AXEygmNz8wHY1DKArMU2kEV1p3RzdSoeXJodsjGKkMbEDimEUmihiLsU855zUQQyblH8RzVpeQfpVZ5FikVywXHrSsyrlWeEg4PBFcvqcsuna/JP1ja1JxnuK619zMWLA9+KwvFFobqzOxcuWCj8ahoYzTX3yRSkcnB/Ot65X959RWRpMK+fCh6hhW3eDEhFSyStPFFd2ctldKHikUrg14r400O58O3rR+WWtmJ8qQHivaQMtzWZ4l02213SptMuU6jMbjqp9qxqU+c6aVZwZ5H4FVpvEEdw7YSAF347Yr1S2Mkyeb5bJvPyg+nrXnnwv0W4Oq6jFcKyi2mClSeoFenNPtl8qOPzJd3QdAPSqpx5NBYiak7mnZtDb4ZztAxRq8C+ct3JIojIwtEUMKwh7x1XaORuqO5lsL61cI5aNOCGHH4VqYJkcW2QExsCBTo/WsfT59Ps7lkiMyA8HP3c1orKHf92QVPemBNPwN3XHaqU5Kvle/JqzOGMW4djVRwdtDQ0ytdPgVn3XMJ/nVy55Iqs6/LkDpUWHcv+HmzZK3+0avS5e4QevFV9OCR20agdRk4rQsEMt6nHyjvTiiG7s6DRokhhM7gYUd6o3MwluzcNgkcKvar2qXCQ26WyjG4VjI4JyBjBqrgakJ8m1M0gyxBx7UzTZGZN3cmsq8u5ZXWIsQoq/Zv5cfynOB+tI0SOi0+XZOWfnC0y5mjkBwcNzwaotcGGyVWPL9TVbd5gBVuhp3Bo2LbfCofIGewpr3crSvgZAHFUPNk2iNGYn0FW4VeVFiK7ST8x74pAyzbO7ruk61ZtsvIIgOS2TUcMWxgpHyjv2q7DtGZSMEcDFBBZkwAFxjFVZZN446U2eVnPyniolOBVAPCMRwM1YeJxbgBeDyaS2Ql/Y1JcSDO1T0FNIGU5LgxqfMUqPUiqO+OTUvMCZSRdr8/lWg8oddjruHoe9UBPa2lwc2UqlhgkDIrREklxdLbR+WoMjjhY1FNthes/nTuI067F6inpLI7iRY9yHvtwRT1LXjiJMrGOXPemTYYrNfSlC37heSf71XpADCVUYwO1OVERAkagKvSmNwCfagTMmzdWh4PIJB/OiltIxFDjGCWJ/WighnyzGccCpUzUCe1WEyKzNxzj92TVZevvVh2/dn6VVVuc0ATZ4rC10n+0bbB71sGQdMVi602dRth70J6gew/DMkaY30rq9xrk/hucaU1dTn860uQ0OzzyRVuz06e4kAcbYz1JqfR7JWzLMob+6PStuI/LtHFTckjtYUs4xFEuAO9TqzN16VPGkUigH73elEceeCalspIYrAHagIPqanDygYWTP0qOLzVJCoCv0pWnMZwyCqSAZcSXAGFJJPFZoiIuGMnzN7VpxRXF3N5akqufmOOlWp4oYMwpEcqM7yOtZzLMm0hTzxkYyfyqzdKls4f+EjnFMLbbksOmauXKCe2yOcVI0Yh1H986C2klzjaMcVk+IGLWsU1xtjlikyqA5OM9K37+6+zoqQJuncYUAcD61npYeXqkK3AWWZvnYHkUAXNGhutSPn36eXAyfuI8/d96WNTFLtbqDjFakLADy1OBu3fSodTjB8u6QcOPm+tY1Kelzqw9TWzIcgjikPWo1bjrS7jmuFneh7VG/rSlqY54poGRyk44qrvG8H0qw5whGaz4n3zSAHIU1pE56z0Ektka7+1KcP7d6uo2QM1WDfNipVztroi7HDua2mupheGTlX6Z7GqrxtFKyHjmiLKqpzV2bZLGtyRuAPzV005XM5KxWTAnYHoBVd1AyT0NWAQTvGBu7VDNluB+NamfMyNeYxUM1sssbeZyCOlWFXC4prKScAgHtmkykzFhR7S7FlPIWicnymPb2qPWrYiyyjkFPm/KmeI554rNlkgLeWwZJouSvsa0LgC4sSY3Dh4wQR3yKTQ2yposLyXUZUe/4VoTp5kzegNN8Pq/lLIRtHSp5MB2I6E1m0BBHEMn2qjMPLuiTwMVrwqpQt0NZOofO3PapC5m2+mqLma5hfyknOZFA5Y1qWESQyggYz1PrToFHkqMcAYqwU3R4HVeaLDFmtbQXAdkEvsRkCoLnassMDKiLMThVXtWhZqrQg4BzWQxe+19pBnyrVcKPU96dhGbpkMeyWNhucSHIYds1cVUj+VF2D0p89v9mkkkByHbJqFW3NjPNWkNMsZyhUng1TlUpwTUpeUHCoGHrUc5YgZXFDApz43dKqXD4wo61bmIPIPSqMuCwPfdUMDZtuLdMqOBXQeHowQ0rjKpzzWFbjMaL64roGYWWjM7EDcKAM7V7vzbp2DkKPu+1Ns1cxhj0Izms95BMVI79avX8ht7WOFWw7c/QUAiAEtdM2eO1XYpDHE3POazkL7iRyx61ft4XZd8hx/s+tBomWLmSaQDP3VHTNWLCJlXLdTTraDzeTwB+tattZsxHyk0DJNLtjEwuXHHar1vG2ZJHH3j8v0qUJtQJ0xQzcfLz2piuPRSYxu+6DzmmSud2MYX2pZcbQi5z/ABe1QlWLBFbOOtIlkgBbJ7ChcZxSlWOY1U5J605lxwTyKoRPA21WYnjGBUJU5z3qST5YAOmetRqAtNCY3bjpSOz4+U45px5OBTVZQjM/OKtAR3EpOIYs7yOTjpVi1jSGLavLH7x9ahgUKSxIYtzn09qsA4qkSxSQKMA9aaTml6UCsZ06iOUrminXw/fbvWigk+TVqdOF5NVwcU4txWZqPlf5cA1FmkJ4zTd2aAHVj6wM6ha/WtYtisrUcvqNsMd/SmiZHsPw7H/EqNdTt5HzKv1rmPh8CNMGBuyeg613FhpNzNKk86oIFOducEmhuwLY0rSTy4lQJuJHGOlWYhcM2ViAx3PSrljAH+d0AUdAO1LJJtmKxj5c4xSvckzbi9mguvLnjMQb7rJzmtFd7RiTIK4/OnuqlVUqGwc5xU8kW4ZLYGOmKqwFeNrjaCqjb71YgSCViMFpDxj3p0S+bG0SfKAMk+lZ1/qIi/cWTcjhmxyaTdi0jcEttZIBM6xk8ZBqleXzyq6WkO/PV2Hb2rO062NyfPunLj+6e9atpKEZwvDgYVccVL1GZILE5f73erdnKRGe4HeqJuC93KkigN2xTbaRxciHJ2sakL2Ldt5brKQgMoPBPp6VnWv77V5bgZPlxBBnuatXUbWcoLE461FpAWW3knRuZpCy5pCTLinLYzyOoq3boJYPIbO09PY1RtWX7Y29dpC8+5rWtsIvy9DQ1cuLa2Ma4ge2mMUnboexqF2Az610OoWwuLdowMuBlDmuZk3I5RxhhXHVpNao9GhV5lZkise9IzcVHnimu/HSudXOggupMAjJ/CqMH7m5ZcgCTkE1akPmyiNep61Fd2rYCkkMnINdFPVHHXnbQFc7vxq6nQVQVgzK3TNXkPA9q1RyIso3y4PUVPZSBG8tjlHOCCapg8U49auMrCki1NEUmKdMdPpTAtTzb/scM0gG/wC7n1qHrg11J3MJbjXG1sYzWBqf9vXMjx25ht4s4GeWNb0pJc1FKBjNMRi2uk38S+ZLqPnkjmNhxUens9pctbSjap5Qds961mbaeKqXcSTjDd+ntQUWdCQJ9qgcnYjb1OfXtUlwgEeQazbK5ltiROm4qdm7++KuGWSQ7TCVHaspFIljdUjOSMFcn61lStu3Gr9zAy25YnpWbLlYWZeoBIqEhkHhzUotQNzGhG6CQhh6VtQj730ry/wDcSWXie8WZiI7yVuPfNepcYwO1UBDHI8cTRjPsadbLFbQ+XGMs3JPepVj8xCc4NOS2xg55FFw6FO6jMluwwQeorIQspJIFdLLGSCawb5PLnIxwaaYEDM2RgmmzSNtzxxTXfBpu3fnk02yUyhcMzMSAcVAg3yop7mp7vcg2gnmoLcZnT61BSOhtgzbQnLAZA+lSapqMd9YxJETgDa4z0b0qtb3SWdysjHGwZOemDXPLI6+KryGGUSWh/ejHTOKY0btsdrr0wpzzUrl7u43jkfpVe2jaYYPUVqWsSxDaAKRpYktIFQDd8xPatO2tGdsNwvQCo7eEBS56ngCteygYIhwelNCJYLaJFCMGwtaloigFgTgCo7a3BXLdqsEsCAqDb60xNhKcDOffFRqu0hyMAHOKRmLNyMc0528yVVXnGMnNBIgOcseCTUkYXbk8GmyDDY7U1TkhfekBMm1W8wnp0pwiZn8zIIJzTLmGTyl2LuA60+CTEZRvlIHWmA1zmXnoBTSrMMjoKUjCb/71Juby9oOM00JjVyHZsHaP51GVEpB5Cg9B3qOadPPjtFkO5z8xHarUa9h0HFWgYbE7ZpxGRS/nQwJ6HFUiOa5Apcy4yAKnahFA7ZPrTuMigDP1AHcv0opdRJ8wD0ooJbPkbNLmo9w96XNTY1FZuCMHmoicdaWU4bFMpMCTeCOeK6jwn8ONT8Q3kd/cSfY7NTn5uGYewq18LPDH9rXz396pFrDjYCOGNe1CZY0WNIkVUGAAB0oQEWjaXpmi2SW1nCMqMbm5JNakKSBPnwQelZokEkwAGM1sxqnk/vH27fWmQ2SRMEslOcHdx70l0pBjY4rP3zXV9m2jYrEMovRc+p9quWllMH33Em925PoPpQkhE8aEnd2FSSsxIA4pN67/KXj+tLNGwlQkjA60MaRHczfZrd9pwZBisiG33sXY5A5NTX1wss8i/wpwD2zRBcJFanepJYdKhmiRagBDA4KrngVePlRfvHcbvbrWTp6O8+6SQkAZA9KtuDJKEhiOD1JouJmTdeb9p+1qp2qePcVZZxuWdOQeeKv3UCpblARwME9qyrMMkUkTjjPy1LYi3qIa70+S4BA2rtGfWqenQGK1jhP34gD+NT2xL6hb2Mi4jcbnq1eW7Q3TTKuc9MdMUhkMYLuWPVhzV/zh5QVT8w7VGiLNGxA2tjORVddyvhufemBrac4kyTnjrVXW4LeSPOf3/8ACAvWo3l8sKyE7h1xVqwuUZxJIFY980nG+hpCfK7nMOwBxk575GMUxyMZzW3r9gkkRvoOufnUVzlzJiI47ivPnBqVj0aVRTVyuZ3jud0YBI9afd3U80AjC7WLfezRpsBmJcjK5q3exBYgMADcM10Uo6HFXd5GHIha+SF5CkSvndnjNbCvkFQc89R3pbKCG4jDSxqxJ701IVhkMaLgjmqehki2QVhBPWpVXK5PeoVbdEB3qTzBhV5zREouzM76XHuHKtwaq7wFYbgNoq9fKv8AZtqpOOTn3rLbAQjnJauuOxzS3DzEYYX7/rTWLHhjmkDL/dGR3pfN2jBHFUIilHPWoGP51NKys/FNaMuuAQKBsS+sSNOW6VixJy30qTT50uraOSM5HQ+xFakkO7T44Djbjmud0WyXTtdu7cSMUcB0Un88VlIa1NG/AS3KseSeKyplPkPjrtNaGrhi0fHGaqXBWKxllc4VUJP5UR1LPKLsXdvIt2jAGOXcOx6816nol+l5YQ3AYMHQZ+tebyiGZWaRhgnIBrpvAF6ktpJanhomwB6j1quUDsop0DMKmSZXOF9Kw2mEetw2a8hkJb2qa8uY7XMm7YijliaOUDVmnijdUZsluMCs7WFi3BlcHA7VR0mW6vme7k2xK3EYPUL61dns0MTuGLPjiptYDIcjdSFz2qNidx4wc03eGJAIyOopCsRX3IOfSqungvdKMdOalu3OcYxTdLCm6fJwAp59KQzbS+0iSy8u6nhBBIZX6isHw9a2011d3lqpEM8mEz6CkvldIhBDNY3LuSF3J8/PrxWvotuLOySIhdyjB2jjNK5SLyKsagKK0LO3eTDAZPpVW3jDMpbpXT6VHGIztByKa1C4yztcENIuAB0rXtxkYHAqJIiQG4xmpvmX7xGB0xWiC5ZHyjimtJhSeQKh3goozgk5wfSoZJS7BFOQW5qWgLKsHUllPtVbDRtvUke1TOwUADjA/Oq0kpZwoxwOaBFhpW25aiydmmBZcAU1lLIufStC3RUg3Y5xQBI0oA2jqKguXHlhmGSTgUn3hkUy6O7PcL6UAR7wfl3YzVbU7iWALbwZe4mHyj0HrV+BF2AuvP0pn2aMXBmXJY+vamhNmVcW8ljpiSkq06yB3fvWvZt5kXmHHzYNR3wjlt5IpB1Uinacu2yRfRQOa0RDZMSOlHakI5pM44piQ4cUuaaOtJO+1MYPI60Bcz7li0pzRTCSSSc0UEs+ScijeKizSZpGw6VvmLZ4qTTbeXUL+CzgyXlcKMVWduPau++B2k/bNal1K4X93AMJkd6TIZ6voNhbaXo1rZQIFEUYDcYy3c1LNNhyByPWpZnQMVVCFzVe5RAuVJGaSHcdbSO1wqW4DStwoI4B9a6a0slRIzdfvpjwc9BWH4YjRrxs/M4HU9q6gmODPqeOaoRV1KxkSZLq2bEsfVQeCvpVkOJUV1GMjpT14dmc7dozkngVXtZxMzPFxCx4J/iPtQAjKDKrAAn0NZ+sarBbkRSTIkj9j3q7PLGqsCuHHvWRqMdmYVluUQtngsM/lUtlIQxEQIzAHzDu65qlLdj7RvhXzUhGGHp6/WrF417cwAJELaAgAseuPaqlikdqJNjDCg5zzmoKN3TXV184co3P0rSssMpx8uaxvD+17VEX5E5JBrftFQfMvCAdaaEytdAEGJ1IUnqKyb2cJIrJGVQHA9WrV1O4BHyYMa/eI7mqTsNgkbaS2AqdcD1oaEihoss91fzX52mNmKIp4ZQK6PPmQfMOR0rEtENleBSMRP0OP1qydbsba4aC5m6dCFpDLNuwCtu43cYpzRBo9qj5uxrGn1+0WfEcUsu84Xahq5ZXd1OQ32fyk/2jzQBI+Vk3YzjhgBmhEGWeAZBPIzyKg1S2urpwI5/Jjz8+3qaomKSCbyLeRxEPvux5bPai4jdt5CA0bfNG4wcGuW1m3aC5k8tHMK9xyBXT2Vs21fnYL7ipXMNjckzKrwSD5s9M1lJXNITcNjm7IIkUUaHJI3EjpUmqofsLMDyCDWze2OmzTGewlWOQj7m7is/UIsWLo/44ppWFJ3dytpEAiCRsd2Oc1Fc4F25H97H4VbshzG3rVW5H+kv1+9WcgQ0cDipEH/LTrimDGPwqxaoJHSPOAzYNOO5VyzfI7afaAcHHPNUrggRLkYYVf1aVftflRn5EAAqjO4eRVYDFdUTmerKu4UrEEYprshkZFHIAOaTB71dwEwBT0UvLGo7sMio27VNYEtfRqOcHJoA2bghQqggbaw9UBW+gvVIG07HORkita+tYLnHnLnacjnFc3rlpY2ts7+ZKG6qu4n8qhopGnrgl+y5hX5kGQD/EKwr29juvDt28assixFWjbqDiquhPqdxbNcNdFYFbAST72f6VBrTq0UksLxx3DqVkRTw4/wAaUVqUcckMk1uo8kHIqbw202k6ysroqwkYfnoK0yBGmApACjHHNZt5EJlyZWjPXGK1sFzp9KuRJf3Ws3W9Y5CRAo6kDirNtbT61KJblDHaIdyL3Yj1puj6hZSaZbrINoVccrwDWxbalZJDt8wFR/dBqXoMfJEAFVcR7Rt+XuKW3D/MmQUAznNVLjWdOVsLI2SD/Cagj1uBVyqyyMwx9w1m3cCpfEJOQWG5ydorGhkb+3J4gxKrGoI9DWdrup3cL297FbyFbec7yehBrO0rUNVur66v7PTg6zvwWbA4pDOquyN1TaGuZpCwytc3c3PiRiSNNth1P36v/D9tVNtdy6lGqM8hCgHgCpEjpkSF7stFCi7BgMB1q5GmeWPNNtYQFDEcmrkcQK5xx60WLTHWEe9huOQD0roLViGCwgNu+8Ky7G3KoWUFsn0qyiXCtlVYGgVjbDSIuzHHvQrKHXzQSgNZsMlwJQsrNj0q+8yyYjRcetO4iS4jEkpljJ2gVHaLgscdKkCbYzGrZ3EZ+lT+VlRg4FO4FZ2LHNNjiJO4YHtVhocdDmnKm0UAFsvQOOKsSyEjanyr7VFHhYyx4NOQEoSaAHLxGQOGpIo9xBY4XPPvSIRks3QcfWnRn5cZzTAfIwY8DoKjVufpTmzuAHeklAQgCqQMgkyz5xxVqAgIB7VVGT+BqzHjywfarM2KSCeKAOaaTg0uePU+lAgIqK6BMZAOKsErtycqarXp2RnJ5PSgCgKKarE980UEM+QS+O9N35NIaQkCobNwZsg+le9/CaxGn+FIN+N9x8/vjtXhOm25vdQgthwXkUfrX0rpdutnaW8MYG2OIKOPakSyxK23OTVK4uFchV7eoqzJzuJ/WqAIznAzVWEdJ4QhLebKMDI27mroL22aWzlVcBguV9Sa5rw5JbjTmFxdCEZ4wec/SrUWsajbTMr273sIziRVwRTAskTanpVssb7A3E2e5HapUMcKC2VMBB8noKzNM1CYtKILQhWbdsZsYqZGvrg4kIhUZ+7yaAH3WxCPMYs7dge9S21hvCyXKAsOg9KLOCOOYZ+c/wB5q1ZGO3I9KhoE7GJrjiKPywOW5rno5lF0kTDK7ua19eky+G5NYLfLMHPqKl6Fpm5YypbzyKchd3AzWy85f5vuRgDt1rCmEaXccxJKSAY4rZtihgM8/odi/ShMbIbiUMjSupVR91cYz703TYHlHmOcZ5+lQDzb+63MSI16CteyZfLaMAAL3qrktlXXLZ5rVPLJLg/LU3h6exv7UJJFH9pjJV1YDORVuziM0uW+6h49zVa90RWvTc2+6GTj5l/rSC4t9brG4IQZU5HFVhMQ+H4rYliklsvnYF17jvWJNGHVg2d61LGX7VVdtxPFVZrdGm4xjdnnpmmWM/loUbuPSrcM8G3YwyfWkmKxLvDIFXACcEiqN9GsyNE3PdSatSqxxs24xn5TzUW5H+WTKg9GxSHYzrOG0uIyk8KrIpwSvBp8un7FJtZm2kYKPyDS3kRima5hO4Y+Ze5qaG6SVFKjtyD1FAyCxs7gsqIoXaeh/wAagurC/Fw5+ztknPy8itLz0Az5jZ9qeuoSBM5zj1pWuNOxhNb3KH97DIPT5at28DQJ9pmG1U5APBNWr7Ubv7P5igYHrWS11LcgPK+70HaqjAhyHby7szHO45FMdQWJI5p0Y4LY5FRecrTGMtjAyTW6Rm0Mi2pcu7AnjFTZz/CMGlMeVJXB96rO7q2OlMBZAucDrVnRUk+1l4x04PFQoVK5KjNafh35beWUnHNDdgHzkkkVm6jBI8OYiiyj7rMucVrPj8aqzrlSKncZwNxo2NQ+z3d/KUm+YBOBmrWtadbWOlGO3iAbgEjk/nWr4it2Nv5sY/eRHcMVm6/eB9NtpI8Aycn604op7GDZu6kqfM5qtqoDoQTg+wqz9ouGG2OVQ/uKjuZJ0jJfaxPfFXcVyx4KmmihmtSFkVG3KrDnFdTa3dsuQ8RRiOcrxXn2lXM2nawlxcMdknBPp6V3tne2cy/u5omGMNuNQykybz7GRvl8osOmMZp0mNpxkA+lZmpafFFMLyDLJ/Gqt29RT0SdLdZbSYyI/TzKzdhnMXY8zw3qFoE86eS4dEXrz2J+lV7aez0u3g05W3zhQCi85PcmtTVY3hsJ8KbQudzygbsn2rI0mDTokZ7KRZ3f70hOWz9O1TcDTdyoGw4yOav+Hbd1EkzA7ScAVm9utaL3bW1iAnLbcqB3NK4JGxLfWtov79xu/hX1qCLXpQcR2gwTwSax7aFnBmuGy555HSrtjB5sy4JwOSam5djYi1TVWOQ8caegWlbVNVGCZhz0+WqyyBptg6Ct2GCOeHCj5v4RVIYyw1qZgEu41J/vAVdS8jMx2v8ALj6VlTW7xcMuGHUAdKbGwQgn0qWFjsNMeKWPeece9Wd+5Sax9DmX7ExJwSeK1IirR8EmtUKw7YSc9KDuPQU8kkD2GKa+QpOcUiRh+Z9vUVI7FeKZbHjeRTpzlx06UANl6BR0zmng7VyR0qLnOc1KW8zAPGKaGPh2yNuJK44GRUMuRIctn6VK5CjZuIzVbpIcVZm2PXgH3qWNsLzUPb0pUYDqapEkr4LKRT0GTx1qMHJyKniIVTxyaBjZMMMGs69kDSBOuOK0tmSTms24j23Az39aBDdqiJAMAnk0U0Hc7Y7cUUEM+OmPNRuecU1npjEnmsjc6z4U2hvfGMK4+WFTIxr3iIy/Z1Kud3v0rx74GQk6zfXezPlxBR+Jr2KN8READiqTJZCbmTBDBGH0qo7AvxhT2FSu4wSRyKrsQ7L6560AkdV4Wgga3LyQI7g8kiukY4QHAAHQYrC8MMv2HGOcnNa18SumzMp+crtU+nvVDsjJ81ir6iI1MTTeWwA7VoyIAqsv3WGVpumWyQW0cMjb1CjcO2fX61akRZHCjhRwAKCCqY1EUjMdvy9fSorGacIEuCGDfcYd6vTwqYmiPIIwfpWXpSSRQyQSDiEnYT6UrDWpS1hT5mcVz9/0P1rfu5CztnFYs6Es7YBXGMGs2aJGpGVl0iCRTnaME1dE7NAqn7pXArI8ObpbG6gfkAkr7VetWZgqEcgdqVxsu2mfJ2odp7mr0IErCK3OW/iNZsjGDaoHLdTW94bijEHnAHLHFVciS0LMZ+wwAOjMSewqZryMMIzGeRkj0pbzhlzyvXFYgkkN5JJnJHY07Aka4XAJVsqT09Ko3dkrSebGOvUUttds06Kcc84FaQkix2xSYzCdCoIK4x2qncrOPniMeOykc10UscM7bh0qpeWUZGU/KswRhLdzxHcYJAw9DkU9dUgmYKykN9Knm0yZ3Bzx7GoJ7CQDZsx7inYorK7LrEcsMn7kgiTIzipI3hut0sRMSg435+9TI7KVCQFYgjn61NHZP5aglUQds0CGNtztDbvQ+tWmt3W0YclsZGKQLCJDbx4OzB461psAeCO2P0polszLqVJrCEqMeaMN+Fc7DIonKdOeBWpcRGOVYGfCLvYD0rICq7yHOHA+U+9bIgff3Jt4o33EBpQh/Go4rmNJ7gSLty2AW70kifaLRY5cKyOHOe5FTu8DJEZY1y5PNAmDalAzpFGSZCOigkVLMScBhg96p3UmoW/NtZxSJ1GODUMGsxzN5d1G0UnQBqYF7eV6VuaYuzTdpPLHNYYw21geDXQRrthTPpmpYFW7inX95byZb+63Sq0OoYUw3aeTIT8rEcGr8j8+3pVW8ijuYWSRQc9M9aSGV5TlvnIIx2Oc54rjdeAtr0W5fKIN4H1NdAEu9OcnBltSeh6rXNeIZrdtaYsjthQN3bFaIbZQilTziBwT7VMZXI+Vk/GkRolViEJQk9uaqEQebsQMvX6VQFPUZXe4VmwyqwP1xXZppthdRpO1uqs4B+Q4rj9RaOKFkEZYkflW3pOvpDoSSMN86jy1jHJJ7VEkUibV2i0yVFtnlluH4WMtwPrUnhzUJyn2ed9yyEujfjyPwqPRNOl/e6lffvLmRTgH+EU7QoANNSSTht5Ke3NY3GbMmx12soZTwQa47V9CsY9QM9qHtpT1aM4z9a6tc5BqjqdsJZVcHvUgY1na3czLGMOQOXzjitC0sZLiNmdwqxkruI61pRIkQWGNcblyavWcSvHsRBgHn3pjKdtp0txbg71j44yKt2mmXVnp7k4kfk5HpWtDBHaRLNdEYPRc9afHJcXROAIoicAY5x6Ucocxz9tGTJlelb2lv9nHmOOpwuexqnLpzC7KW0pAbG7jpWg1nIIljRywU55ppBzGhMiXEO0Y8zufWsaS1bzvLI5rYtcRoFYEN1JpzqdgmK4LcDIosUmVYdsYSNOgGGrRsZcEqe9ZgGyTAq7aKQwYjigZs4/c0yc/J+FN3fIADxSOf4e56UEsWLaLfcwyM0ydlbDKakmAWAL61AF3NigQ5TxU8SoE3N1qEj0qViCoxTQyKUEtkmiMYoCnJOc0o4q0ZsRjxSAc0NSgjiqRJPbrlgc4xU561EhAGMVKM0wFHHtWbMxkvCSRxV+Q/Lis+cNEWfgls4pCK1uwO/n+KiobP/WOO+aKAPjpqQ0UVmanqfwL+7qX++teoj7rUUUgKUnQ/WoE/wBYv1FFFUgOw8L/APHmf941s3n/AB5n6UUVRMhkff6VYj7fWiiggWb75qk/WaiigcDDuPvt9KzJvuNRRWTNiXwv/wAvFadl/wAfX4UUVIiS/wDvp+NdF4c/5B6/7xooqkDLl/8AdFYa/wCtn+hooq2IZYf8fkf0P8q1F/493oorOQC2f+qp1x9wUUVKEgg6fjUE/wDrDRRVFIYetUrjrL9RRRSAoad/yEp622+8KKKaIZz+t/8AIRb/AK5N/MViD7zfWiithC338P8AuVDc/wDIPtv96iihEs2B9wf7tYevf6xPrRRTYFvT/wDj3jrqv+WUf+7RRSAqy1m6h/qz9aKKSGV4/wDUt9K43X/+P65/CiiqQIqxf8eo+tVf+XiiirGiO+/1ZpPCf/ISi/67UUVMikd4fuSf7pqhp3/HjF+NFFc8txl0fdqtc9qKKOgD0/1w/wB0Vp6N/wCzCiikgLWuf6+D6itOX70P1FFFaslbkFl/x8XP+9V6270UUIFuLP0T61Pcf8eEP1ooqWUjNb/j4/GtGP7goopFstRfcFPH+vT8aKKCR939xfrUEf3/AMKKKAHmndhRRTY2IvSkaiiqRkxH/pSDqKKKtAWR1qYdKKKaJGP0qnf/AHBRRQBmWv8Ar3ooopCZ/9k=" alt="Kanta T." style="width:100%;height:100%;object-fit:cover;object-position:center top;">
                </div>
                <!-- Name card under photo -->
                <div class="bg-ink-900 text-white rounded-2xl px-5 py-3 text-center shadow-lg" style="width:220px;">
                    <p class="font-semibold text-sm">Kanta T. (Gift)</p>
                    <p class="text-xs text-sage-300 mt-0.5">BD & Operations Manager</p>
                    <div class="flex justify-center gap-1 mt-2">
                        <span class="px-2 py-0.5 bg-white/10 rounded text-[10px]">10+ Yrs</span>
                        <span class="px-2 py-0.5 bg-white/10 rounded text-[10px]">Bangkok</span>
                        <span class="px-2 py-0.5 bg-sage-600 rounded text-[10px]">M.Sc.</span>
                    </div>
                </div>
            </div>

        </div>
    </div>
</section>

<!-- ═══════════════ EXPERIENCE TIMELINE ═══════════════ -->
<section id="experience" class="py-24 bg-ink-50 border-y border-ink-100">
    <div class="max-w-4xl mx-auto px-5 lg:px-10">
        <div class="text-center mb-16">
            <p class="section-label mb-3">Career History</p>
            <h3 class="section-title text-3xl lg:text-4xl text-ink-900">Professional Experience</h3>
        </div>

        <!-- Timeline Wrapper -->
        <div class="relative pl-10">
            <div class="tl-line"></div>

            <!-- ── JOB ENTRY TEMPLATE ── -->

            <!-- 1. Ookbee U — BD & Ops Manager (2024–Present) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-sage-500"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">BD & Operations Manager</p>
                            <p class="text-sage-600 font-semibold text-sm">Ookbee U · Digital Platforms</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">2024 – Present</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed mb-4">Lead business model planning, go-to-market strategy, and full marketing execution across 6 workstreams: Social Community, Brand Content, Ads/Lead Gen, Influencer/KOL, and Communication. Manage team & agency, marketing budget, and Looker Studio big-data dashboards.</p>
                    <div class="space-y-2">
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Joydom:</b> Revenue-share artist partnership with zero upfront cost → <b>1M+ THB</b> from a brand-new platform</span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Joy Character Chat (AI):</b> Full product launch in <b>1 month</b> under reduced headcount — maintained existing revenue + new AI income</span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>TikTok & Lemon8:</b> Content seeding strategy → 1-week viral Twitter trend + creator program <b>150 → 600+ active/day (4×)</b></span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 2. S.C.S. Sportswear (Nov 2022 – Dec 2023) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-700"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Marketing Manager</p>
                            <p class="text-sage-600 font-semibold text-sm">S.C.S. Sportswear</p>
                        </div>
                        <div class="flex flex-col items-end gap-1">
                            <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Nov 2022 – Dec 2023</span>
                            <span class="text-[10px] font-medium text-ink-300 pr-1">1 yr 2 mo</span>
                        </div>
                    </div>
                    <!-- Brand tags -->
                    <div class="flex flex-wrap gap-1.5 mb-4">
                        <span class="text-[10px] font-semibold text-ink-600 bg-ink-50 border border-ink-200 px-2 py-0.5 rounded-full">Breaker</span>
                        <span class="text-[10px] font-semibold text-ink-600 bg-ink-50 border border-ink-200 px-2 py-0.5 rounded-full">Catcha</span>
                        <span class="text-[10px] font-semibold text-ink-600 bg-ink-50 border border-ink-200 px-2 py-0.5 rounded-full">Popteen</span>
                        <span class="text-[10px] font-semibold text-ink-600 bg-ink-50 border border-ink-200 px-2 py-0.5 rounded-full">Poplove</span>
                        <span class="text-[10px] font-semibold text-sage-600 bg-sage-50 border border-sage-200 px-2 py-0.5 rounded-full">TVC Production</span>
                        <span class="text-[10px] font-semibold text-sage-600 bg-sage-50 border border-sage-200 px-2 py-0.5 rounded-full">Music Marketing</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed mb-4">Planned and executed multi-brand marketing across online & offline channels. Managed TVC production, brand ambassador contracts, agency coordination, and media budgets (Facebook Ads, TikTok Ads, Lazada, Shopee).</p>
                    <div class="space-y-2">
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Breaker × Dept. of Physical Education (The Baek TVC):</b> Repositioned Breaker as a Gen Z youth brand through student ambassador storytelling</span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Breaker ISUS:</b> Launched B2B vocational go-to-market strategy into trade/professional channels</span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>E-commerce growth of 50–80%</b> on own digital retail platform</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 3. Amarin Book Center (Jun 2022 – Nov 2022) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-400"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Marketing & Partnership Section Manager</p>
                            <p class="text-sage-600 font-semibold text-sm">Amarin Book Center</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Jun 2022 – Nov 2022 · 6 mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed">Developed full-funnel marketing strategy (awareness → conversion), designed quarterly campaign plans, and pitched customized media partnership packages to business clients. Coordinated internal teams and external partners throughout campaign delivery.</p>
                </div>
            </div>

            <!-- 4. Ookbee — Community Manager (Nov 2021 – May 2022) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-400"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Community Manager</p>
                            <p class="text-sage-600 font-semibold text-sm">Ookbee · A Duang Horoscope Platform</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Nov 2021 – May 2022 · 7 mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed">Managed campaign roadmaps, media sale packages, KOL partnerships, and live streaming monetization. Grew LIVE streaming revenue through new format adoption and drove incremental platform income.</p>
                </div>
            </div>

            <!-- 5. S.C.S. Footwear — Asst. MM (Mar 2021 – Nov 2021) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-400"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Assistant Marketing Manager / Online Lead</p>
                            <p class="text-sage-600 font-semibold text-sm">S.C.S. Footwear</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Mar 2021 – Nov 2021 · 9 mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed mb-3">Managed online media plans, Facebook/TikTok/Lazada/Shopee ads, stock forecasting, and campaign reporting. Initiated footwear sponsorship for Tegball athletes independently.</p>
                    <div class="space-y-2">
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Breaker SB Pro:</b> Storytelling campaign built around Thailand national skateboarding team</span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Toxic (school shoes):</b> Partnered with K6Y (hip-hop) + JONE 500 for Gen Z co-branding & distribution</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 6. Chounan (Jan 2021 – Mar 2021) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-300"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Marketing Manager</p>
                            <p class="text-sage-600 font-semibold text-sm">Chounan Food Manufacturing</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Jan 2021 – Mar 2021 · 2 mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed">Managed promotions across food delivery, marketplace, and e-wallet platforms. Handled KOL relationships and 'SOULSHI' sushi restaurant launch. Achieved <b>50% revenue growth</b> from delivery & e-commerce.</p>
                </div>
            </div>

            <!-- 7. Ookbee / Ookbee U — Senior Marketing Officer (Mar 2018 – Jan 2021) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-sage-600"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Senior Marketing Officer</p>
                            <p class="text-sage-600 font-semibold text-sm">Ookbee / Ookbee U · Digital Platforms</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Mar 2018 – Jan 2021 · 2y 11mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed mb-4">Led growth campaigns, community programs, and offline Book Fair events. Used AppsFlyer, Power BI, and Google Analytics for acquisition, retention, and reporting to MD/CMO.</p>
                    <div class="space-y-2">
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Q1/2019:</b> Reduced offline Book Fair event losses by <b>~100%</b> through redesigned logistics & operation flow</span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Q3/2019:</b> Grew aduang fortune-teller MAU and revenue by <b>100%</b></span>
                        </div>
                        <div class="flex items-start gap-2 text-xs text-ink-600">
                            <i class="fas fa-trophy text-sage-500 mt-0.5 w-3 flex-shrink-0"></i>
                            <span><b>Q2/2020:</b> Launched 2 partnership campaigns in new revenue models (Joylada & aduang)</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 8. Shichida Thailand (Mar 2017 – Mar 2018) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-300"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Marketing Executive</p>
                            <p class="text-sage-600 font-semibold text-sm">Shichida Thailand</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Mar 2017 – Mar 2018 · 1y</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed">Planned influencer programs, managed marketing budget, ran co-promotion events including Thailand Baby Best Buy. Achieved <b>new revenue high</b> since institution launch and significantly expanded brand awareness.</p>
                </div>
            </div>

            <!-- 9. Yushi Group (Aug 2016 – Mar 2017) -->
            <div class="relative mb-12">
                <div class="tl-dot bg-ink-300"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Marketing Executive</p>
                            <p class="text-sage-600 font-semibold text-sm">Yushi Group</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Aug 2016 – Mar 2017 · 8 mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed">Managed product launches into retail channels (TV Direct, True Select, 7-Catalog, Thai Watsadu) and e-commerce platforms (Lazada, Shopee, 11street). Launched <b>'Shinsen by Yushi'</b> successfully to market.</p>
                </div>
            </div>

            <!-- 10. TrueVisions Group (Mar 2012 – Aug 2016) -->
            <div class="relative mb-4">
                <div class="tl-dot bg-ink-300"></div>
                <div class="bg-white rounded-2xl border border-ink-200 p-6 hover:shadow-md transition-shadow">
                    <div class="flex flex-wrap justify-between items-start gap-2 mb-3">
                        <div>
                            <p class="font-bold text-ink-900 text-base">Marketing & PR Executive</p>
                            <p class="text-sage-600 font-semibold text-sm">TrueVisions Group</p>
                        </div>
                        <span class="text-xs font-semibold text-ink-400 bg-ink-100 px-3 py-1 rounded-full whitespace-nowrap">Mar 2012 – Aug 2016 · 4y 5mo</span>
                    </div>
                    <p class="text-xs text-ink-500 leading-relaxed">Managed PR for large-scale press conferences and commercial campaigns. Wrote press releases, approved MC scripts, coordinated mass media partners, and reported PR Value to Marketing Director. Supported subscriber growth and retention initiatives.</p>
                </div>
            </div>

        </div>

        <!-- Education Block -->
        <div class="mt-16 bg-white rounded-2xl border border-ink-200 p-8">
            <p class="section-label mb-5">Education</p>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="flex items-start gap-4">
                    <div class="w-10 h-10 rounded-xl bg-sage-100 flex items-center justify-center text-sage-600 flex-shrink-0">
                        <i class="fas fa-graduation-cap text-sm"></i>
                    </div>
                    <div>
                        <p class="font-bold text-ink-900 text-sm">M.Sc. Community Psychology</p>
                        <p class="text-sage-600 text-sm">Kasetsart University</p>
                        <p class="text-xs text-ink-400 mt-1">2022 – 2024 · GPAX 3.70</p>
                    </div>
                </div>
                <div class="flex items-start gap-4">
                    <div class="w-10 h-10 rounded-xl bg-ink-100 flex items-center justify-center text-ink-500 flex-shrink-0">
                        <i class="fas fa-university text-sm"></i>
                    </div>
                    <div>
                        <p class="font-bold text-ink-900 text-sm">B.A. Hotel Studies</p>
                        <p class="text-sage-600 text-sm">Kasetsart University (Sriracha)</p>
                        <p class="text-xs text-ink-400 mt-1">2008 – 2012 · GPAX 2.85</p>
                    </div>
                </div>
            </div>
            <div class="border-t border-ink-100 mt-6 pt-6">
                <p class="section-label mb-4">Certifications</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill"><i class="fas fa-certificate text-sage-500 text-xs"></i> Supervisor & Leadership — KU 2022</span>
                    <span class="skill-pill"><i class="fas fa-certificate text-sage-500 text-xs"></i> MCP Excellence Series — TBS 2020</span>
                    <span class="skill-pill"><i class="fas fa-certificate text-sage-500 text-xs"></i> PDPA for Strategic Marketing — KU 2020</span>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ═══════════════ CAMPAIGNS ═══════════════ -->
<section id="campaigns" class="py-24 bg-white">
    <div class="max-w-6xl mx-auto px-5 lg:px-10">
        <div class="text-center mb-16">
            <p class="section-label mb-3">Video Work</p>
            <h3 class="section-title text-3xl lg:text-4xl text-ink-900">Brand Campaigns</h3>
        </div>

        <!-- Breaker -->
        <div class="mb-16">
            <div class="flex items-center gap-4 mb-8">
                <span class="text-xs font-black tracking-widest text-white bg-ink-900 px-4 py-2 rounded-lg uppercase">
                    <i class="fas fa-shoe-prints mr-2"></i> Breaker Brand — S.C.S. Sportswear
                </span>
                <div class="h-px bg-ink-100 flex-grow"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

                <!-- 1: พีท - อิทธิชา (Futsal) -->
                <a href="https://www.youtube.com/watch?v=0noEjfVV8rc" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/0noEjfVV8rc/mqdefault.jpg" alt="Breaker Futsal Pete" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">Brand Story · Futsal</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">พีท - อิทธิชา ประภาพันธ์ การเกิดใหม่ของ 'หมาล่าเนื้อ' สู่ 'นักล่าฝัน' เพื่อวันไปฟุตซอลโลก</h5>
                    </div>
                </a>

                <!-- 2: Breaker ใส่ให้เต็มทุกความรู้สึก (TVC) -->
                <a href="https://www.youtube.com/watch?v=7UFKFspBkMw" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/7UFKFspBkMw/mqdefault.jpg" alt="Breaker TVC Commercial" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">TVC Commercial</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">Breaker ใส่ให้เต็มทุกความรู้สึก</h5>
                    </div>
                </a>

                <!-- 3: BrandTalk สเก็ตบอร์ด -->
                <a href="https://www.youtube.com/watch?v=Kz3mUOqRJFA" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/Kz3mUOqRJFA/mqdefault.jpg" alt="Breaker BrandTalk Skateboard" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">BrandTalk</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">จากเด็กสุพรรณฯ สู่การเป็นแชมป์สเก็ตบอร์ดเอเชียนบีชเกมส์</h5>
                    </div>
                </a>

                <!-- 4: Breaker SB Pro (regular card, same size) -->
                <a href="https://www.youtube.com/watch?v=0A6IT56qXOc&list=PLvEFjuZxCA6Yt1mikkCpy4_nQnbWmgbOd" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/0A6IT56qXOc/mqdefault.jpg" alt="Breaker SB Pro" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 right-3 bg-sage-600 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase">
                                <i class="fas fa-list mr-1"></i> Playlist
                            </span>
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">Campaign Series · Breaker SB Pro</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">Breaker X SB Pro X ผู้ร่วมทดสอบท่าน</h5>
                    </div>
                </a>

                <!-- 5: Breaker x SGUB Cola Red -->
                <a href="https://www.youtube.com/watch?v=LCNzZDv85q8" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/LCNzZDv85q8/mqdefault.jpg" alt="Breaker SGUB Cola Red" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">New Product Collaboration</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">𝐁𝐑𝐄𝐀𝐊𝐄𝐑 𝐱 𝐒𝐆𝐔𝐁 𝐂𝐎𝐋𝐀 𝐑𝐄𝐃</h5>
                    </div>
                </a>

                <!-- 6: ซีรีส์เบรกเกอร์ "ไม่ว่าคุณจะแบกอะไรไว้" -->
                <a href="https://www.youtube.com/watch?v=LcdF5Fo0hmg&list=PLvEFjuZxCA6Z7jgwxFh4IRdsuvjzo0OQI" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/LcdF5Fo0hmg/mqdefault.jpg" alt="Breaker The Baek Series" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 right-3 bg-sage-600 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase">
                                <i class="fas fa-list mr-1"></i> Playlist
                            </span>
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">Campaign Series · The Baek</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">ซีรีส์เบรกเกอร์ "ไม่ว่าคุณจะแบกอะไรไว้ เราจะแบกคุณเอง"</h5>
                    </div>
                </a>

            </div>
        </div>

        <!-- Popteen -->
        <div>
            <div class="flex items-center gap-4 mb-8">
                <span class="text-xs font-black tracking-widest text-white bg-ink-900 px-4 py-2 rounded-lg uppercase">
                    <i class="fas fa-star mr-2"></i> Popteen Brand — S.C.S. Footwear
                </span>
                <div class="h-px bg-ink-100 flex-grow"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

                <!-- Popteen 1 (new) -->
                <a href="https://www.youtube.com/watch?v=U2Vfqt-byKI" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/U2Vfqt-byKI/mqdefault.jpg" alt="Popteen Campaign" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">Branded Variety Content · Popteen</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">POPTEEN X อ๊ะอาย 4EVE | POPTEEN The Secret Idols</h5>
                    </div>
                </a>

                <!-- Popteen Music Marketing 1 -->
                <a href="https://www.youtube.com/watch?v=hKqdGabXBUk&list=RDhKqdGabXBUk&start_radio=1" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/hKqdGabXBUk/mqdefault.jpg" alt="Popteen Music Marketing 1" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 right-3 bg-ink-700 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase">
                                <i class="fas fa-music mr-1"></i> Music Mkt
                            </span>
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">Music Marketing · Popteen</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">หายใจเป็นเธอ | Gracy & Sita [Official MV]</h5>
                    </div>
                </a>

                <!-- Popteen Music Marketing 2 -->
                <a href="https://www.youtube.com/watch?v=untrdYx3yYE&list=RDuntrdYx3yYE&start_radio=1" target="_blank" class="vid-card rounded-2xl overflow-hidden border border-ink-100 block bg-white">
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/untrdYx3yYE/mqdefault.jpg" alt="Popteen Music Marketing 2" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 right-3 bg-ink-700 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase">
                                <i class="fas fa-music mr-1"></i> Music Mkt
                            </span>
                            <div class="w-11 h-11 rounded-full bg-white/90 flex items-center justify-center shadow-lg">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">Music Marketing · Popteen</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">FLI:P 'ปีน(ตัว)ท็อป' [OFFICIAL MV]</h5>
                    </div>
                </a>

            </div>
        </div>

        <!-- Joylada -->
        <div class="mt-16">
            <div class="flex items-center gap-4 mb-8">
                <span class="text-xs font-black tracking-widest text-white bg-ink-900 px-4 py-2 rounded-lg uppercase">
                    <i class="fas fa-video mr-2"></i> Joylada — Live Talk Series
                </span>
                <div class="h-px bg-ink-100 flex-grow"></div>
                <a href="https://www.youtube.com/playlist?list=PLzgqSDWk_CvwoWzBGbJzONn1NX6xPuvEx" target="_blank"
                   class="flex items-center gap-1.5 text-[11px] font-semibold text-ink-400 hover:text-sage-600 transition whitespace-nowrap">
                    See more <i class="fas fa-arrow-right text-[9px]"></i>
                </a>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

                <!-- JoyLiveกะTalk x จุง -->
                <a href="https://www.youtube.com/watch?v=2PWU9Emjw3Q&list=PLzgqSDWk_CvwoWzBGbJzONn1NX6xPuvEx&index=33&t=1125s" target="_blank"
                   class="group vid-card rounded-2xl overflow-hidden border border-sage-200 block bg-white relative">
                    <!-- Highlight glow -->
                    <div class="absolute inset-0 rounded-2xl ring-2 ring-sage-300/60 pointer-events-none"></div>
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/2PWU9Emjw3Q/mqdefault.jpg" alt="JoyLiveกะTalk จุง" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 left-3 bg-sage-600 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase tracking-wide">
                                <i class="fas fa-star mr-1"></i> Highlight
                            </span>
                            <div class="w-12 h-12 rounded-full bg-white/90 flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4 bg-gradient-to-b from-sage-50 to-white">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">JoyLiveกะTalk · Live Series</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">JoyLiveกะTalk x จุง - ดัง By Popteen</h5>
                    </div>
                </a>

                <!-- JoyLiveกะTalk x WIZZLE -->
                <a href="https://www.youtube.com/watch?v=YSGRvDNrRGg&list=PLzgqSDWk_CvwoWzBGbJzONn1NX6xPuvEx&index=31" target="_blank"
                   class="group vid-card rounded-2xl overflow-hidden border border-sage-200 block bg-white relative">
                    <div class="absolute inset-0 rounded-2xl ring-2 ring-sage-300/60 pointer-events-none"></div>
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/YSGRvDNrRGg/mqdefault.jpg" alt="JoyLiveกะTalk WIZZLE" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 left-3 bg-sage-600 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase tracking-wide">
                                <i class="fas fa-star mr-1"></i> Highlight
                            </span>
                            <div class="w-12 h-12 rounded-full bg-white/90 flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4 bg-gradient-to-b from-sage-50 to-white">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">JoyLiveกะTalk · Live Series</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">JoyLiveกะTalk x WIZZLE</h5>
                    </div>
                </a>

                <!-- JoyLiveกะTalk x Mindy -->
                <a href="https://www.youtube.com/watch?v=G3oV7KQ9ZbQ&list=PLzgqSDWk_CvwoWzBGbJzONn1NX6xPuvEx&index=13" target="_blank"
                   class="group vid-card rounded-2xl overflow-hidden border border-sage-200 block bg-white relative">
                    <div class="absolute inset-0 rounded-2xl ring-2 ring-sage-300/60 pointer-events-none"></div>
                    <div class="aspect-video relative overflow-hidden">
                        <img src="https://img.youtube.com/vi/G3oV7KQ9ZbQ/mqdefault.jpg" alt="JoyLiveกะTalk Mindy" class="w-full h-full object-cover">
                        <div class="vid-overlay absolute inset-0 flex items-center justify-center">
                            <span class="absolute top-3 left-3 bg-sage-600 text-white text-[9px] font-bold px-2 py-0.5 rounded-full uppercase tracking-wide">
                                <i class="fas fa-star mr-1"></i> Highlight
                            </span>
                            <div class="w-12 h-12 rounded-full bg-white/90 flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform">
                                <i class="fas fa-play text-ink-900 text-xs ml-0.5"></i>
                            </div>
                        </div>
                    </div>
                    <div class="p-4 bg-gradient-to-b from-sage-50 to-white">
                        <p class="text-[10px] font-bold text-sage-600 uppercase tracking-widest mb-1">JoyLiveกะTalk · Live Series</p>
                        <h5 class="text-sm font-semibold text-ink-900 leading-snug">JoyLiveกะTalk x Mindy</h5>
                    </div>
                </a>

            </div>
        </div>

        <!-- Influencer / Seeding -->
        <div class="mt-16">
            <div class="flex items-center gap-4 mb-8">
                <span class="text-xs font-black tracking-widest text-white bg-ink-900 px-4 py-2 rounded-lg uppercase">
                    <i class="fas fa-seedling mr-2"></i> Influencer & Seeding Network
                </span>
                <div class="h-px bg-ink-100 flex-grow"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

                <a href="https://vt.tiktok.com/ZSuwKtvdv/" target="_blank"
                   class="group rounded-2xl border border-ink-100 bg-ink-50 p-6 hover:border-sage-300 hover:bg-sage-50 transition-all flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-5">
                            <div class="w-10 h-10 rounded-full bg-ink-900 text-white flex items-center justify-center">
                                <i class="fab fa-tiktok text-sm"></i>
                            </div>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-ink-200 text-ink-700 px-2 py-0.5 rounded">TikTok Live</span>
                        </div>
                        <h5 class="text-sm font-semibold text-ink-900 mb-2 group-hover:text-sage-600 transition">TikTok Short-Form Seeding Campaign</h5>
                        <p class="text-xs text-ink-400 leading-relaxed">Micro-influencer content seeding strategy driving FYP placement and algorithm virality on TikTok & Lemon8</p>
                    </div>
                    <div class="mt-5 flex items-center justify-between text-xs font-semibold text-ink-700 group-hover:text-sage-600">
                        <span>ดูตัวอย่างผลงาน</span>
                        <i class="fas fa-arrow-right text-[10px] transform group-hover:translate-x-1 transition-transform"></i>
                    </div>
                </a>

                <a href="https://www.tiktok.com/@beddor.dek/video/7618092185363172615" target="_blank"
                   class="group rounded-2xl border border-ink-100 bg-ink-50 p-6 hover:border-sage-300 hover:bg-sage-50 transition-all flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-5">
                            <div class="w-10 h-10 rounded-full bg-ink-900 text-white flex items-center justify-center">
                                <i class="fab fa-tiktok text-sm"></i>
                            </div>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-ink-200 text-ink-700 px-2 py-0.5 rounded">KOL Creator</span>
                        </div>
                        <h5 class="text-sm font-semibold text-ink-900 mb-2 group-hover:text-sage-600 transition">KOL Integration @beddor.dek</h5>
                        <p class="text-xs text-ink-400 leading-relaxed">Lifestyle student creator collaboration — authentic product storytelling to Gen Z footwear audience</p>
                    </div>
                    <div class="mt-5 flex items-center justify-between text-xs font-semibold text-ink-700 group-hover:text-sage-600">
                        <span>ดูตัวอย่างผลงาน</span>
                        <i class="fas fa-arrow-right text-[10px] transform group-hover:translate-x-1 transition-transform"></i>
                    </div>
                </a>

                <a href="https://www.instagram.com/reels/DYZiLR-psSZ/" target="_blank"
                   class="group rounded-2xl border border-ink-100 bg-ink-50 p-6 hover:border-sage-300 hover:bg-sage-50 transition-all flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-5">
                            <div class="w-10 h-10 rounded-full bg-gradient-to-tr from-yellow-500 via-pink-500 to-purple-600 text-white flex items-center justify-center">
                                <i class="fab fa-instagram text-sm"></i>
                            </div>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-ink-200 text-ink-700 px-2 py-0.5 rounded">IG Reels</span>
                        </div>
                        <h5 class="text-sm font-semibold text-ink-900 mb-2 group-hover:text-sage-600 transition">Instagram Reels Seeding</h5>
                        <p class="text-xs text-ink-400 leading-relaxed">Short-form content seeding on IG Reels targeting female high school students with lifestyle-forward brand narrative</p>
                    </div>
                    <div class="mt-5 flex items-center justify-between text-xs font-semibold text-ink-700 group-hover:text-sage-600">
                        <span>ดูตัวอย่างผลงาน</span>
                        <i class="fas fa-arrow-right text-[10px] transform group-hover:translate-x-1 transition-transform"></i>
                    </div>
                </a>

            </div>
        </div>

    </div>
</section>

<!-- ═══════════════ PR & MEDIA ═══════════════ -->
<section id="media" class="py-24 bg-ink-50 border-t border-ink-100">
    <div class="max-w-6xl mx-auto px-5 lg:px-10">
        <div class="text-center mb-16">
            <p class="section-label mb-3">Press Coverage</p>
            <h3 class="section-title text-3xl lg:text-4xl text-ink-900">PR & Media Placements</h3>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-5">

            <!-- Card 1: Brandthink / Catcha -->
            <a href="https://www.brandthink.me/content/catcha" target="_blank"
               class="group bg-white rounded-2xl border border-ink-100 overflow-hidden hover:shadow-md transition-all flex flex-col">
                <div class="aspect-video relative overflow-hidden flex-shrink-0">
                    <img src="https://btdigitalstorage.sgp1.digitaloceanspaces.com/2021/10/3009_Catcha_1111-1024x538.jpg"
                         alt="Catcha Campaign" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end p-3">
                        <span class="text-[9px] font-black tracking-widest bg-sage-600 px-2 py-0.5 rounded text-white uppercase">BRANDTHINK</span>
                    </div>
                </div>
                <div class="p-4 flex-grow">
                    <span class="text-[10px] font-bold text-sage-600 uppercase tracking-wider">Platform Strategy</span>
                    <h5 class="text-sm font-semibold text-ink-900 mt-1 mb-2 leading-snug group-hover:text-sage-600 transition">CATCHA Campaign Insight</h5>
                    <p class="text-xs text-ink-400 leading-relaxed">วิเคราะห์เจาะลึกทิศทางการตลาดพลิกโฉมแบรนด์ Catcha ผ่าน Content ที่ทรงพลัง</p>
                </div>
                <div class="px-4 pb-4">
                    <span class="text-xs font-semibold text-ink-700 group-hover:text-sage-600 transition flex items-center gap-1">
                        อ่านบทความ <i class="fas fa-arrow-up-right-from-square text-[9px]"></i>
                    </span>
                </div>
            </a>

            <!-- Card 2: Workpoint / Poplove S4 -->
            <a href="https://www.workpointtoday.com/poplove-season4" target="_blank"
               class="group bg-white rounded-2xl border border-ink-100 overflow-hidden hover:shadow-md transition-all flex flex-col">
                <div class="aspect-video relative overflow-hidden flex-shrink-0">
                    <img src="https://images.workpointtoday.com/workpointnews/2023/02/15141937/1676445573_17359_image18.webp"
                         alt="Poplove Season 4" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end p-3">
                        <span class="text-[9px] font-black tracking-widest bg-red-600 px-2 py-0.5 rounded text-white uppercase">WORKPOINT TODAY</span>
                    </div>
                </div>
                <div class="p-4 flex-grow">
                    <span class="text-[10px] font-bold text-sage-600 uppercase tracking-wider">Media & PR Placement</span>
                    <h5 class="text-sm font-semibold text-ink-900 mt-1 mb-2 leading-snug group-hover:text-sage-600 transition">Poplove Season 4</h5>
                    <p class="text-xs text-ink-400 leading-relaxed">กระจายข่าวผ่านเครือข่ายสำนักข่าวบันเทิงยักษ์ใหญ่เพื่อการเข้าถึงระดับประเทศ</p>
                </div>
                <div class="px-4 pb-4">
                    <span class="text-xs font-semibold text-ink-700 group-hover:text-sage-600 transition flex items-center gap-1">
                        อ่านบทความ <i class="fas fa-arrow-up-right-from-square text-[9px]"></i>
                    </span>
                </div>
            </a>

            <!-- Card 3: Workpoint / Poplove x Popteen -->
            <a href="https://www.workpointtoday.com/poplove-popteen-season4" target="_blank"
               class="group bg-white rounded-2xl border border-ink-100 overflow-hidden hover:shadow-md transition-all flex flex-col">
                <div class="aspect-video relative overflow-hidden flex-shrink-0">
                    <img src="https://images.workpointtoday.com/workpointnews/2023/01/31184232/1675165348_95692_web-_01.webp"
                         alt="Poplove Popteen" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end p-3">
                        <span class="text-[9px] font-black tracking-widest bg-red-600 px-2 py-0.5 rounded text-white uppercase">WORKPOINT TODAY</span>
                    </div>
                </div>
                <div class="p-4 flex-grow">
                    <span class="text-[10px] font-bold text-sage-600 uppercase tracking-wider">Cross-Brand Alignment</span>
                    <h5 class="text-sm font-semibold text-ink-900 mt-1 mb-2 leading-snug group-hover:text-sage-600 transition">Poplove × Popteen</h5>
                    <p class="text-xs text-ink-400 leading-relaxed">ประสานพลังความร่วมมือระหว่างผลิตภัณฑ์ในเครือข่ายสร้างสถิติยอดการมีส่วนร่วม</p>
                </div>
                <div class="px-4 pb-4">
                    <span class="text-xs font-semibold text-ink-700 group-hover:text-sage-600 transition flex items-center gap-1">
                        อ่านบทความ <i class="fas fa-arrow-up-right-from-square text-[9px]"></i>
                    </span>
                </div>
            </a>

            <!-- Card 4: LINE TODAY / Breaker Futsal -->
            <a href="https://today.line.me/th/v3/article/562B1V" target="_blank"
               class="group bg-white rounded-2xl border border-ink-100 overflow-hidden hover:shadow-md transition-all flex flex-col">
                <div class="aspect-video relative overflow-hidden flex-shrink-0 bg-gradient-to-br from-green-700 to-green-900 flex items-center justify-center">
                    <i class="fab fa-line text-white text-5xl opacity-30"></i>
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end p-3">
                        <span class="text-[9px] font-black tracking-widest bg-green-600 px-2 py-0.5 rounded text-white uppercase">LINE TODAY</span>
                    </div>
                </div>
                <div class="p-4 flex-grow">
                    <span class="text-[10px] font-bold text-sage-600 uppercase tracking-wider">Product PR</span>
                    <h5 class="text-sm font-semibold text-ink-900 mt-1 mb-2 leading-snug group-hover:text-sage-600 transition">Breaker Futsal Zodiac Pack</h5>
                    <p class="text-xs text-ink-400 leading-relaxed">รองเท้าฟุตซอลประจำราศี 12 จักรราศี เปิดตัวสนับสนุนนักกีฬาไทย</p>
                </div>
                <div class="px-4 pb-4">
                    <span class="text-xs font-semibold text-ink-700 group-hover:text-sage-600 transition flex items-center gap-1">
                        อ่านบทความ <i class="fas fa-arrow-up-right-from-square text-[9px]"></i>
                    </span>
                </div>
            </a>

        </div>
    </div>
</section>

<!-- ═══════════════ SKILLS ═══════════════ -->
<section id="skills" class="py-24 bg-white border-t border-ink-100">
    <div class="max-w-6xl mx-auto px-5 lg:px-10">
        <div class="text-center mb-16">
            <p class="section-label mb-3">Expertise</p>
            <h3 class="section-title text-3xl lg:text-4xl text-ink-900">Core Skills & Tools</h3>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">

            <div>
                <p class="text-xs font-bold uppercase tracking-widest text-ink-400 mb-5 border-b border-ink-100 pb-3">Strategy & Growth</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill">Go-to-Market Planning</span>
                    <span class="skill-pill">Platform Monetization</span>
                    <span class="skill-pill">Revenue Optimization</span>
                    <span class="skill-pill">Creator Program Design</span>
                    <span class="skill-pill">UGC Expansion</span>
                    <span class="skill-pill">Budget Management</span>
                </div>
            </div>

            <div>
                <p class="text-xs font-bold uppercase tracking-widest text-ink-400 mb-5 border-b border-ink-100 pb-3">Partnership & Operations</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill">Strategic Partnerships</span>
                    <span class="skill-pill">KOL / Influencer Mgmt</span>
                    <span class="skill-pill">Negotiation</span>
                    <span class="skill-pill">Team Leadership</span>
                    <span class="skill-pill">KPI Management</span>
                    <span class="skill-pill">Agency Coordination</span>
                </div>
            </div>

            <div>
                <p class="text-xs font-bold uppercase tracking-widest text-ink-400 mb-5 border-b border-ink-100 pb-3">Data & Analytics</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill"><i class="fas fa-chart-bar text-sage-500 text-[10px]"></i> Looker Studio</span>
                    <span class="skill-pill"><i class="fas fa-chart-bar text-sage-500 text-[10px]"></i> Metabase</span>
                    <span class="skill-pill"><i class="fas fa-chart-bar text-sage-500 text-[10px]"></i> Power BI</span>
                    <span class="skill-pill">AppsFlyer</span>
                    <span class="skill-pill">Google Analytics</span>
                    <span class="skill-pill">Facebook Pixel</span>
                    <span class="skill-pill">UTM Tracking</span>
                </div>
            </div>

            <div>
                <p class="text-xs font-bold uppercase tracking-widest text-ink-400 mb-5 border-b border-ink-100 pb-3">Digital Advertising</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill">Facebook Ads</span>
                    <span class="skill-pill">Google Ads</span>
                    <span class="skill-pill">TikTok Ads</span>
                    <span class="skill-pill">Apple Search Ads</span>
                    <span class="skill-pill">Lazada Ads</span>
                    <span class="skill-pill">Shopee Ads</span>
                </div>
            </div>

            <div>
                <p class="text-xs font-bold uppercase tracking-widest text-ink-400 mb-5 border-b border-ink-100 pb-3">AI & Productivity</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill"><i class="fas fa-robot text-sage-500 text-[10px]"></i> Claude AI</span>
                    <span class="skill-pill"><i class="fas fa-robot text-sage-500 text-[10px]"></i> ChatGPT</span>
                    <span class="skill-pill"><i class="fas fa-robot text-sage-500 text-[10px]"></i> Gemini</span>
                    <span class="skill-pill">Google Workspace</span>
                    <span class="skill-pill">MS Office</span>
                    <span class="skill-pill">Canva</span>
                </div>
            </div>

            <div>
                <p class="text-xs font-bold uppercase tracking-widest text-ink-400 mb-5 border-b border-ink-100 pb-3">Community Platforms</p>
                <div class="flex flex-wrap gap-2">
                    <span class="skill-pill"><i class="fab fa-tiktok text-[10px]"></i> TikTok</span>
                    <span class="skill-pill">Lemon8</span>
                    <span class="skill-pill"><i class="fab fa-instagram text-[10px] text-pink-500"></i> Instagram</span>
                    <span class="skill-pill"><i class="fab fa-facebook text-[10px] text-blue-600"></i> Facebook</span>
                    <span class="skill-pill">Discord</span>
                    <span class="skill-pill">LINE OA</span>
                    <span class="skill-pill">Twitter/X</span>
                </div>
            </div>

        </div>
    </div>
</section>

<!-- ═══════════════ FOOTER ═══════════════ -->
<footer class="py-16 bg-ink-900 text-white">
    <div class="max-w-6xl mx-auto px-5 lg:px-10 flex flex-col items-center text-center">
        <p class="section-label text-ink-500 mb-6">Get in Touch</p>
        <a href="mailto:kanta.gubgift@gmail.com"
           class="section-title text-2xl md:text-4xl text-white hover:text-sage-300 transition-colors underline underline-offset-8 decoration-ink-700">
            kanta.gubgift@gmail.com
        </a>
        <div class="flex gap-6 mt-8 text-ink-500">
            <a href="tel:0969392444" class="hover:text-white transition text-sm">096-939-2444</a>
            <span>·</span>
            <a href="https://www.linkedin.com/in/kanta-thanawatthanawut" target="_blank" class="hover:text-white transition text-sm">LinkedIn</a>
            <span>·</span>
            <span class="text-sm">Bangkok, Thailand</span>
        </div>
        <p class="text-[10px] text-ink-700 uppercase tracking-widest mt-10">© 2026 Kanta Thanawatthanawut · Strategic Portfolio</p>
    </div>
</footer>

</body>
</html>
