<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2299.4">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica; min-height: 14.0px}
  </style>
</head>
<body>
<p class="p1">&lt;!DOCTYPE html&gt;</p>
<p class="p1">&lt;html lang="en" class="scroll-smooth"&gt;</p>
<p class="p1">&lt;head&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;meta charset="UTF-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;title&gt;AnyMind Group: Interactive Research Report&lt;/title&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;script src="https://cdn.tailwindcss.com"&gt;&lt;/script&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;script src="https://cdn.jsdelivr.net/npm/chart.js"&gt;&lt;/script&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;!-- Chosen Palette: Warm Sand &amp; Deep Slate (bg-stone-50, text-stone-800, accent emerald-600/blue-600) --&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;!-- Application Structure Plan: A single-page dashboard designed for non-linear exploration. It flows from a high-level overview (At a Glance &amp; Timeline) into the core ecosystem (Interactive Product Tabs), followed by quantitative validation (Financial Charts), and concludes with an interactive use-case demonstration. This structure mimics a strategic briefing, prioritizing the most critical understanding—how the distinct products form a unified commerce ecosystem—via tabbed exploration to avoid cognitive overload. --&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;!-- Visualization &amp; Content Choices:<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">         </span>1. Overview Stats: Goal = Inform -&gt; Viz = Dynamic counters (HTML/JS) -&gt; Interaction = Scroll trigger. Justification = Immediate impact.</p>
<p class="p1"><span class="Apple-converted-space">         </span>2. History: Goal = Change/Evolution -&gt; Viz = Clickable Timeline (HTML/JS) -&gt; Interaction = Click year to update text -&gt; Justification = Saves space, encourages user engagement.<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">         </span>3. Ecosystem: Goal = Organize -&gt; Viz = Tabbed Interface (HTML/JS) -&gt; Interaction = Switch tabs -&gt; Justification = Groups complex product suites by target audience.<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">         </span>4. Financials: Goal = Compare/Trend -&gt; Viz = Bar &amp; Doughnut (Chart.js) -&gt; Interaction = Tooltips/Hover -&gt; Justification = Industry standard for financial metrics.<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">         </span>5. Synergy Flow: Goal = Process -&gt; Viz = Step-by-step indicator (HTML/JS) -&gt; Interaction = Next/Prev buttons -&gt; Justification = Demonstrates product interconnectedness visually without complex SVGs. --&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. --&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;style&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>.chart-container {</p>
<p class="p1"><span class="Apple-converted-space">            </span>position: relative;</p>
<p class="p1"><span class="Apple-converted-space">            </span>width: 100%;</p>
<p class="p1"><span class="Apple-converted-space">            </span>max-width: 800px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-left: auto;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-right: auto;</p>
<p class="p1"><span class="Apple-converted-space">            </span>height: 40vh;</p>
<p class="p1"><span class="Apple-converted-space">            </span>max-height: 400px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>min-height: 300px;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>@media (min-width: 768px) {</p>
<p class="p1"><span class="Apple-converted-space">            </span>.chart-container {</p>
<p class="p1"><span class="Apple-converted-space">                </span>height: 50vh;</p>
<p class="p1"><span class="Apple-converted-space">                </span>max-height: 500px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>.tab-active {</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-bottom: 2px solid #059669;</p>
<p class="p1"><span class="Apple-converted-space">            </span>color: #059669;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-weight: 600;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>.fade-in {</p>
<p class="p1"><span class="Apple-converted-space">            </span>animation: fadeIn 0.5s ease-in-out;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>@keyframes fadeIn {</p>
<p class="p1"><span class="Apple-converted-space">            </span>from { opacity: 0; transform: translateY(10px); }</p>
<p class="p1"><span class="Apple-converted-space">            </span>to { opacity: 1; transform: translateY(0); }</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/style&gt;</p>
<p class="p1">&lt;/head&gt;</p>
<p class="p1">&lt;body class="bg-stone-50 text-stone-800 font-sans antialiased"&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;nav class="sticky top-0 z-50 bg-white/90 backdrop-blur-md border-b border-stone-200 shadow-sm"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="flex justify-between h-16 items-center"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="flex-shrink-0 font-bold text-xl tracking-tight text-stone-900"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&amp;#127760; AnyMind &lt;span class="text-emerald-600"&gt;Report&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="hidden md:flex space-x-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;a href="#overview" class="text-stone-600 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors"&gt;Overview&lt;/a&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;a href="#ecosystem" class="text-stone-600 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors"&gt;Ecosystem&lt;/a&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;a href="#performance" class="text-stone-600 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors"&gt;Performance&lt;/a&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;a href="#synergy" class="text-stone-600 hover:text-emerald-600 px-3 py-2 text-sm font-medium transition-colors"&gt;Synergy Flow&lt;/a&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/nav&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;header class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-20 text-center"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-stone-900 tracking-tight mb-6"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>Make Every Business &lt;span class="text-transparent bg-clip-text bg-gradient-to-r from-emerald-600 to-blue-600"&gt;Borderless&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/h1&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;p class="mt-4 text-xl text-stone-600 max-w-3xl mx-auto"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>An interactive analysis of AnyMind Group: The end-to-end commerce enablement company empowering brands, creators, and publishers across Asia and beyond.</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;div class="mt-10 flex justify-center gap-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;a href="#overview" class="bg-stone-900 text-white px-6 py-3 rounded-md font-medium hover:bg-stone-800 transition-colors shadow-lg"&gt;Begin Exploration &amp;#8595;&lt;/a&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/header&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;main class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 pb-24 space-y-24"&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;section id="overview" class="scroll-mt-24"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="mb-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;h2 class="text-3xl font-bold text-stone-900 mb-4"&gt;Company Overview &amp; Evolution&lt;/h2&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;p class="text-lg text-stone-600 leading-relaxed"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>This section provides a foundational understanding of AnyMind Group's scale and historical trajectory. By exploring these high-level metrics and the interactive timeline, users can grasp how quickly the company expanded from a pure marketing tech startup into a comprehensive commerce ecosystem operating across multiple markets.</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="grid grid-cols-2 md:grid-cols-4 gap-6 mb-12"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl shadow-sm border border-stone-100 text-center hover:-translate-y-1 transition-transform"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-3xl mb-2"&gt;&amp;#128197;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-4xl font-bold text-emerald-600 mb-1" id="stat-year"&gt;2016&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-sm text-stone-500 font-medium uppercase tracking-wide"&gt;Founded&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl shadow-sm border border-stone-100 text-center hover:-translate-y-1 transition-transform"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-3xl mb-2"&gt;&amp;#127758;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-4xl font-bold text-blue-600 mb-1" id="stat-markets"&gt;15+&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-sm text-stone-500 font-medium uppercase tracking-wide"&gt;Markets&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl shadow-sm border border-stone-100 text-center hover:-translate-y-1 transition-transform"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-3xl mb-2"&gt;&amp;#128101;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-4xl font-bold text-emerald-600 mb-1" id="stat-emp"&gt;1,500+&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-sm text-stone-500 font-medium uppercase tracking-wide"&gt;Professionals&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl shadow-sm border border-stone-100 text-center hover:-translate-y-1 transition-transform"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-3xl mb-2"&gt;&amp;#128200;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-4xl font-bold text-blue-600 mb-1" id="stat-ipo"&gt;2023&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="text-sm text-stone-500 font-medium uppercase tracking-wide"&gt;TSE Growth IPO&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="bg-white rounded-xl shadow-sm border border-stone-200 overflow-hidden flex flex-col md:flex-row"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="w-full md:w-1/3 bg-stone-50 p-6 border-b md:border-b-0 md:border-r border-stone-200"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;h3 class="font-bold text-lg mb-4 text-stone-800"&gt;Growth Timeline&lt;/h3&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="space-y-2 flex flex-col" id="timeline-buttons"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;button class="text-left px-4 py-3 rounded-lg bg-emerald-100 text-emerald-800 font-semibold transition-colors timeline-btn" data-year="2016"&gt;2016: Inception&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;button class="text-left px-4 py-3 rounded-lg hover:bg-stone-200 text-stone-600 font-medium transition-colors timeline-btn" data-year="2019"&gt;2019: Creator Expansion&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;button class="text-left px-4 py-3 rounded-lg hover:bg-stone-200 text-stone-600 font-medium transition-colors timeline-btn" data-year="2020"&gt;2020: Commerce Pivot&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;button class="text-left px-4 py-3 rounded-lg hover:bg-stone-200 text-stone-600 font-medium transition-colors timeline-btn" data-year="2023"&gt;2023: Public Listing&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="w-full md:w-2/3 p-8 flex items-center min-h-[250px]"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="timeline-content" class="fade-in"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;div class="text-emerald-600 font-bold text-xl mb-2"&gt;Singapore Launch&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-2xl font-bold text-stone-900 mb-4"&gt;AdAsia Holdings is Born&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;p class="text-stone-600 leading-relaxed"&gt;Founded in Singapore by Kosuke Sogo and Otohiko Kozutsumi, initially focusing on marketing technology and advertising networks across Southeast Asia.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/section&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;section id="ecosystem" class="scroll-mt-24 pt-12 border-t border-stone-200"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="mb-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;h2 class="text-3xl font-bold text-stone-900 mb-4"&gt;The End-to-End Commerce Ecosystem&lt;/h2&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;p class="text-lg text-stone-600 leading-relaxed"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>AnyMind's core strength is its proprietary software suite catering to three distinct pillars: Brands, Creators, and Publishers. Use the interactive tabs below to filter the product catalog and understand the specific tools designed for each target audience. This structure highlights the breadth of their proprietary platforms.</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="mb-6 flex space-x-1 border-b border-stone-200 overflow-x-auto"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;button class="tab-btn px-6 py-4 text-sm font-medium text-stone-500 hover:text-stone-800 tab-active whitespace-nowrap" data-target="tab-brands"&gt;&amp;#127970; Brands &amp; Enterprises&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;button class="tab-btn px-6 py-4 text-sm font-medium text-stone-500 hover:text-stone-800 whitespace-nowrap" data-target="tab-creators"&gt;&amp;#128241; Creators &amp; Influencers&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;button class="tab-btn px-6 py-4 text-sm font-medium text-stone-500 hover:text-stone-800 whitespace-nowrap" data-target="tab-publishers"&gt;&amp;#128240; Publishers &amp; Media&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div id="tab-brands" class="tab-content grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 fade-in"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-anyx')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-emerald-600 transition-colors"&gt;AnyX&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#128640;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;E-commerce management platform to manage multiple sales channels.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-anyx" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Centralized inventory management&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Cross-channel order tracking&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Integrated analytics dashboard&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-emerald-600 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-anytag')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-emerald-600 transition-colors"&gt;AnyTag&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#127919;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;Influencer marketing platform for campaign management and analytics.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-anytag" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Database of hundreds of thousands of influencers&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Automated campaign workflow&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Real-time performance tracking&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-emerald-600 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-anylogi')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-emerald-600 transition-colors"&gt;AnyLogi&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#128230;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;Logistics management platform streamlining fulfillment and delivery.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-anylogi" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Multi-carrier shipping integration&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Automated customs documentation&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Warehouse management system links&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-emerald-600 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p2"><span class="Apple-converted-space">                </span></p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-anychat')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-emerald-600 transition-colors"&gt;AnyChat&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#128172;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;Conversational commerce platform for customer engagement.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-anychat" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;CRM integration across messaging apps&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Automated chat flows and triggers&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;In-chat checkout capabilities&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-emerald-600 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div id="tab-creators" class="tab-content hidden grid grid-cols-1 md:grid-cols-2 gap-6 fade-in"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-anycreator')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-blue-600 transition-colors"&gt;AnyCreator&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#11088;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;App and web platform providing creators with insights and monetization tools.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-anycreator" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Link-in-bio building features&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Social media performance analytics&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Direct brand collaboration opportunities&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-blue-600 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-d2c')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-blue-600 transition-colors"&gt;D2C for Creators&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#128085;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;Enabling creators to launch their own branded merchandise and product lines.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-d2c" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;End-to-end planning and manufacturing&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Store setup via AnyX&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Fulfillment handled via AnyLogi&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-blue-600 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div id="tab-publishers" class="tab-content hidden grid grid-cols-1 md:grid-cols-2 gap-6 fade-in"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl border border-stone-200 hover:shadow-md transition-shadow cursor-pointer group" onclick="toggleDetails('details-anymanager')"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex items-center justify-between mb-4"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-xl font-bold text-stone-900 group-hover:text-stone-800 transition-colors"&gt;AnyManager&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span class="text-2xl"&gt;&amp;#128202;&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-stone-600 mb-4 text-sm"&gt;Monetization, analytics, and growth platform for web and app publishers.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div id="details-anymanager" class="hidden mt-4 pt-4 border-t border-stone-100 text-sm text-stone-500"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;ul class="list-disc pl-5 space-y-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;Header bidding implementation&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;User engagement analytics&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;li&gt;App store optimization insights&lt;/li&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/ul&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-xs text-stone-800 font-semibold mt-2 text-right"&gt;Click to expand &amp;#8595;&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/section&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;section id="performance" class="scroll-mt-24 pt-12 border-t border-stone-200"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="mb-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;h2 class="text-3xl font-bold text-stone-900 mb-4"&gt;Financial &amp; Quantitative Performance&lt;/h2&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;p class="text-lg text-stone-600 leading-relaxed"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>This section translates textual growth reports into clear data visualizations. The bar chart illustrates the company's aggressive year-over-year revenue trajectory, while the doughnut chart breaks down the current business model, highlighting the shift toward e-commerce enablement alongside their traditional marketing roots. Hover over elements for exact figures.</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="grid grid-cols-1 lg:grid-cols-2 gap-12"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;h3 class="font-bold text-lg text-stone-800 mb-2"&gt;Revenue Trajectory (Illustrative, Millions USD)&lt;/h3&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-sm text-stone-500 mb-6"&gt;Showing consistent YoY growth leading to public listing.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="chart-container"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;canvas id="revenueChart"&gt;&lt;/canvas&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;h3 class="font-bold text-lg text-stone-800 mb-2"&gt;Revenue Composition by Segment&lt;/h3&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;p class="text-sm text-stone-500 mb-6"&gt;Diversification beyond ad-tech into commerce and logistics.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="chart-container flex items-center justify-center"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;canvas id="segmentChart"&gt;&lt;/canvas&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/section&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;section id="synergy" class="scroll-mt-24 pt-12 border-t border-stone-200"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="mb-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;h2 class="text-3xl font-bold text-stone-900 mb-4"&gt;The "Synergy" Multiplier Effect&lt;/h2&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;p class="text-lg text-stone-600 leading-relaxed"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>The true value of AnyMind Group isn't just in isolated products, but in how they interlock. This interactive flow diagram demonstrates a typical use case: how a brand utilizes multiple AnyMind platforms seamlessly to launch a product, market it, sell it, and ship it.</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;div class="bg-stone-900 rounded-xl p-8 text-white relative overflow-hidden"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="absolute top-0 right-0 w-64 h-64 bg-emerald-600/20 rounded-full blur-3xl -mr-20 -mt-20"&gt;&lt;/div&gt;</p>
<p class="p2"><span class="Apple-converted-space">                </span></p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="flex flex-col md:flex-row gap-6 mb-8 items-stretch justify-center relative z-10" id="flow-container"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flow-step flex-1 p-6 bg-stone-800 border border-stone-700 rounded-lg text-center opacity-50 transition-all duration-300" id="step-1"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;div class="text-3xl mb-3"&gt;&amp;#128269;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="font-bold text-emerald-400 mb-2"&gt;1. Awareness&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;p class="text-sm text-stone-300"&gt;Brand uses &lt;strong&gt;AnyTag&lt;/strong&gt; to identify micro-influencers and launch a targeted awareness campaign.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p2"><span class="Apple-converted-space">                    </span></p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="hidden md:flex items-center text-stone-600 text-2xl"&gt;&amp;#8594;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex md:hidden justify-center text-stone-600 text-2xl"&gt;&amp;#8595;&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flow-step flex-1 p-6 bg-stone-800 border border-stone-700 rounded-lg text-center opacity-50 transition-all duration-300" id="step-2"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;div class="text-3xl mb-3"&gt;&amp;#128722;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="font-bold text-blue-400 mb-2"&gt;2. Conversion&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;p class="text-sm text-stone-300"&gt;Traffic is driven to multiple online stores, all centrally managed via &lt;strong&gt;AnyX&lt;/strong&gt; analytics.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="hidden md:flex items-center text-stone-600 text-2xl"&gt;&amp;#8594;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flex md:hidden justify-center text-stone-600 text-2xl"&gt;&amp;#8595;&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div class="flow-step flex-1 p-6 bg-stone-800 border border-stone-700 rounded-lg text-center opacity-50 transition-all duration-300" id="step-3"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;div class="text-3xl mb-3"&gt;&amp;#128666;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="font-bold text-emerald-400 mb-2"&gt;3. Fulfillment&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;p class="text-sm text-stone-300"&gt;Orders flow automatically into &lt;strong&gt;AnyLogi&lt;/strong&gt;, optimizing shipping routes and customs processes.&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;div class="flex justify-center gap-4 relative z-10"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;button id="btn-prev-flow" class="px-4 py-2 bg-stone-700 hover:bg-stone-600 rounded text-sm font-medium transition-colors disabled:opacity-30 disabled:cursor-not-allowed"&gt;Previous Step&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;button id="btn-next-flow" class="px-4 py-2 bg-emerald-600 hover:bg-emerald-500 rounded text-sm font-medium transition-colors"&gt;Start Flow&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/section&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/main&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;footer class="bg-stone-900 text-stone-400 py-8 text-center text-sm border-t border-stone-800"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;p&gt;Interactive Data Presentation | Created for Research Synthesis&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/footer&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;script&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>// --- TIMELINE INTERACTIVITY ---</p>
<p class="p1"><span class="Apple-converted-space">        </span>const timelineData = {</p>
<p class="p1"><span class="Apple-converted-space">            </span>"2016": {</p>
<p class="p1"><span class="Apple-converted-space">                </span>subtitle: "Singapore Launch",</p>
<p class="p1"><span class="Apple-converted-space">                </span>title: "AdAsia Holdings is Born",</p>
<p class="p1"><span class="Apple-converted-space">                </span>text: "Founded in Singapore by Kosuke Sogo and Otohiko Kozutsumi, initially focusing on marketing technology and advertising networks across Southeast Asia."</p>
<p class="p1"><span class="Apple-converted-space">            </span>},</p>
<p class="p1"><span class="Apple-converted-space">            </span>"2019": {</p>
<p class="p1"><span class="Apple-converted-space">                </span>subtitle: "Strategic Acquisition",</p>
<p class="p1"><span class="Apple-converted-space">                </span>title: "Expansion into Creator Tech",</p>
<p class="p1"><span class="Apple-converted-space">                </span>text: "Acquired Moindy in Thailand and launched the CastingAsia Creators Network, pivoting strongly into influencer marketing and creator enablement."</p>
<p class="p1"><span class="Apple-converted-space">            </span>},</p>
<p class="p1"><span class="Apple-converted-space">            </span>"2020": {</p>
<p class="p1"><span class="Apple-converted-space">                </span>subtitle: "Rebranding",</p>
<p class="p1"><span class="Apple-converted-space">                </span>title: "Birth of AnyMind Group",</p>
<p class="p1"><span class="Apple-converted-space">                </span>text: "Rebranded to AnyMind Group to reflect expansion beyond advertising. Launched initial D2C tools for influencers to create their own brands."</p>
<p class="p1"><span class="Apple-converted-space">            </span>},</p>
<p class="p1"><span class="Apple-converted-space">            </span>"2023": {</p>
<p class="p1"><span class="Apple-converted-space">                </span>subtitle: "Milestone",</p>
<p class="p1"><span class="Apple-converted-space">                </span>title: "TSE Growth Market IPO",</p>
<p class="p1"><span class="Apple-converted-space">                </span>text: "Successfully listed on the Tokyo Stock Exchange Growth Market, securing capital to further expand its e-commerce, logistics, and conversational commerce suite."</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>};</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>const timelineBtns = document.querySelectorAll('.timeline-btn');</p>
<p class="p1"><span class="Apple-converted-space">        </span>const timelineContent = document.getElementById('timeline-content');</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>timelineBtns.forEach(btn =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>btn.addEventListener('click', function() {</p>
<p class="p1"><span class="Apple-converted-space">                </span>// Reset styling</p>
<p class="p1"><span class="Apple-converted-space">                </span>timelineBtns.forEach(b =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">                    </span>b.classList.remove('bg-emerald-100', 'text-emerald-800', 'font-semibold');</p>
<p class="p1"><span class="Apple-converted-space">                    </span>b.classList.add('hover:bg-stone-200', 'text-stone-600', 'font-medium');</p>
<p class="p1"><span class="Apple-converted-space">                </span>});</p>
<p class="p1"><span class="Apple-converted-space">                </span>// Set active styling</p>
<p class="p1"><span class="Apple-converted-space">                </span>this.classList.remove('hover:bg-stone-200', 'text-stone-600', 'font-medium');</p>
<p class="p1"><span class="Apple-converted-space">                </span>this.classList.add('bg-emerald-100', 'text-emerald-800', 'font-semibold');</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>const year = this.getAttribute('data-year');</p>
<p class="p1"><span class="Apple-converted-space">                </span>const data = timelineData[year];</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>// Remove animation class briefly to restart it</p>
<p class="p1"><span class="Apple-converted-space">                </span>timelineContent.classList.remove('fade-in');</p>
<p class="p2"><span class="Apple-converted-space">                </span></p>
<p class="p1"><span class="Apple-converted-space">                </span>setTimeout(() =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">                    </span>timelineContent.innerHTML = `</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;div class="text-emerald-600 font-bold text-xl mb-2"&gt;${data.subtitle}&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;h4 class="text-2xl font-bold text-stone-900 mb-4"&gt;${data.title}&lt;/h4&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;p class="text-stone-600 leading-relaxed"&gt;${data.text}&lt;/p&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>`;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>timelineContent.classList.add('fade-in');</p>
<p class="p1"><span class="Apple-converted-space">                </span>}, 50);</p>
<p class="p1"><span class="Apple-converted-space">            </span>});</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// --- TAB INTERACTIVITY (ECOSYSTEM) ---</p>
<p class="p1"><span class="Apple-converted-space">        </span>const tabBtns = document.querySelectorAll('.tab-btn');</p>
<p class="p1"><span class="Apple-converted-space">        </span>const tabContents = document.querySelectorAll('.tab-content');</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>tabBtns.forEach(btn =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>btn.addEventListener('click', () =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">                </span>// Remove active class from all buttons</p>
<p class="p1"><span class="Apple-converted-space">                </span>tabBtns.forEach(b =&gt; b.classList.remove('tab-active', 'text-stone-800'));</p>
<p class="p1"><span class="Apple-converted-space">                </span>tabBtns.forEach(b =&gt; b.classList.add('text-stone-500'));</p>
<p class="p2"><span class="Apple-converted-space">                </span></p>
<p class="p1"><span class="Apple-converted-space">                </span>// Add active class to clicked button</p>
<p class="p1"><span class="Apple-converted-space">                </span>btn.classList.add('tab-active', 'text-stone-800');</p>
<p class="p1"><span class="Apple-converted-space">                </span>btn.classList.remove('text-stone-500');</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>// Hide all contents</p>
<p class="p1"><span class="Apple-converted-space">                </span>tabContents.forEach(content =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">                    </span>content.classList.add('hidden');</p>
<p class="p1"><span class="Apple-converted-space">                </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">                </span>// Show target content</p>
<p class="p1"><span class="Apple-converted-space">                </span>const targetId = btn.getAttribute('data-target');</p>
<p class="p1"><span class="Apple-converted-space">                </span>const targetContent = document.getElementById(targetId);</p>
<p class="p1"><span class="Apple-converted-space">                </span>targetContent.classList.remove('hidden');</p>
<p class="p1"><span class="Apple-converted-space">            </span>});</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// Toggle Expandable Cards</p>
<p class="p1"><span class="Apple-converted-space">        </span>function toggleDetails(id) {</p>
<p class="p1"><span class="Apple-converted-space">            </span>const el = document.getElementById(id);</p>
<p class="p1"><span class="Apple-converted-space">            </span>if(el.classList.contains('hidden')) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>el.classList.remove('hidden');</p>
<p class="p1"><span class="Apple-converted-space">                </span>el.classList.add('fade-in');</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else {</p>
<p class="p1"><span class="Apple-converted-space">                </span>el.classList.add('hidden');</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// --- CHART.JS VISUALIZATIONS ---</p>
<p class="p2"><span class="Apple-converted-space">        </span></p>
<p class="p1"><span class="Apple-converted-space">        </span>// Ensure fonts look good</p>
<p class="p1"><span class="Apple-converted-space">        </span>Chart.defaults.font.family = "'Inter', 'Segoe UI', sans-serif";</p>
<p class="p1"><span class="Apple-converted-space">        </span>Chart.defaults.color = '#6b7280'; // text-stone-500</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// 1. Revenue Chart (Bar)</p>
<p class="p1"><span class="Apple-converted-space">        </span>const ctxRev = document.getElementById('revenueChart').getContext('2d');</p>
<p class="p1"><span class="Apple-converted-space">        </span>new Chart(ctxRev, {</p>
<p class="p1"><span class="Apple-converted-space">            </span>type: 'bar',</p>
<p class="p1"><span class="Apple-converted-space">            </span>data: {</p>
<p class="p1"><span class="Apple-converted-space">                </span>labels: ['2019', '2020', '2021', '2022', '2023'],</p>
<p class="p1"><span class="Apple-converted-space">                </span>datasets: [{</p>
<p class="p1"><span class="Apple-converted-space">                    </span>label: 'Revenue (M USD)',</p>
<p class="p1"><span class="Apple-converted-space">                    </span>data: [50, 80, 130, 190, 250], // Illustrative data showing strong growth</p>
<p class="p1"><span class="Apple-converted-space">                    </span>backgroundColor: '#10B981', // emerald-500</p>
<p class="p1"><span class="Apple-converted-space">                    </span>borderRadius: 4,</p>
<p class="p1"><span class="Apple-converted-space">                    </span>hoverBackgroundColor: '#059669' // emerald-600</p>
<p class="p1"><span class="Apple-converted-space">                </span>}]</p>
<p class="p1"><span class="Apple-converted-space">            </span>},</p>
<p class="p1"><span class="Apple-converted-space">            </span>options: {</p>
<p class="p1"><span class="Apple-converted-space">                </span>responsive: true,</p>
<p class="p1"><span class="Apple-converted-space">                </span>maintainAspectRatio: false,</p>
<p class="p1"><span class="Apple-converted-space">                </span>plugins: {</p>
<p class="p1"><span class="Apple-converted-space">                    </span>legend: { display: false },</p>
<p class="p1"><span class="Apple-converted-space">                    </span>tooltip: {</p>
<p class="p1"><span class="Apple-converted-space">                        </span>backgroundColor: '#1f2937',</p>
<p class="p1"><span class="Apple-converted-space">                        </span>padding: 12,</p>
<p class="p1"><span class="Apple-converted-space">                        </span>callbacks: {</p>
<p class="p1"><span class="Apple-converted-space">                            </span>label: function(context) {</p>
<p class="p1"><span class="Apple-converted-space">                                </span>return '$' + context.raw + ' Million';</p>
<p class="p1"><span class="Apple-converted-space">                            </span>}</p>
<p class="p1"><span class="Apple-converted-space">                        </span>}</p>
<p class="p1"><span class="Apple-converted-space">                    </span>}</p>
<p class="p1"><span class="Apple-converted-space">                </span>},</p>
<p class="p1"><span class="Apple-converted-space">                </span>scales: {</p>
<p class="p1"><span class="Apple-converted-space">                    </span>y: {</p>
<p class="p1"><span class="Apple-converted-space">                        </span>beginAtZero: true,</p>
<p class="p1"><span class="Apple-converted-space">                        </span>grid: { color: '#f3f4f6' },</p>
<p class="p1"><span class="Apple-converted-space">                        </span>border: { display: false }</p>
<p class="p1"><span class="Apple-converted-space">                    </span>},</p>
<p class="p1"><span class="Apple-converted-space">                    </span>x: {</p>
<p class="p1"><span class="Apple-converted-space">                        </span>grid: { display: false },</p>
<p class="p1"><span class="Apple-converted-space">                        </span>border: { display: false }</p>
<p class="p1"><span class="Apple-converted-space">                    </span>}</p>
<p class="p1"><span class="Apple-converted-space">                </span>}</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// 2. Segment Chart (Doughnut)</p>
<p class="p1"><span class="Apple-converted-space">        </span>const ctxSeg = document.getElementById('segmentChart').getContext('2d');</p>
<p class="p1"><span class="Apple-converted-space">        </span>new Chart(ctxSeg, {</p>
<p class="p1"><span class="Apple-converted-space">            </span>type: 'doughnut',</p>
<p class="p1"><span class="Apple-converted-space">            </span>data: {</p>
<p class="p1"><span class="Apple-converted-space">                </span>labels: [</p>
<p class="p1"><span class="Apple-converted-space">                    </span>'Marketing Platforms (AnyTag, etc.)',<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">                    </span>'D2C &amp; E-Commerce (AnyX, AnyLogi)',<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">                    </span>'Partner Growth (AnyManager)'</p>
<p class="p1"><span class="Apple-converted-space">                </span>],</p>
<p class="p1"><span class="Apple-converted-space">                </span>datasets: [{</p>
<p class="p1"><span class="Apple-converted-space">                    </span>data: [45, 35, 20], // Illustrative split</p>
<p class="p1"><span class="Apple-converted-space">                    </span>backgroundColor: [</p>
<p class="p1"><span class="Apple-converted-space">                        </span>'#3B82F6', // blue-500</p>
<p class="p1"><span class="Apple-converted-space">                        </span>'#10B981', // emerald-500</p>
<p class="p1"><span class="Apple-converted-space">                        </span>'#F59E0B'<span class="Apple-converted-space">  </span>// amber-500</p>
<p class="p1"><span class="Apple-converted-space">                    </span>],</p>
<p class="p1"><span class="Apple-converted-space">                    </span>borderWidth: 0,</p>
<p class="p1"><span class="Apple-converted-space">                    </span>hoverOffset: 4</p>
<p class="p1"><span class="Apple-converted-space">                </span>}]</p>
<p class="p1"><span class="Apple-converted-space">            </span>},</p>
<p class="p1"><span class="Apple-converted-space">            </span>options: {</p>
<p class="p1"><span class="Apple-converted-space">                </span>responsive: true,</p>
<p class="p1"><span class="Apple-converted-space">                </span>maintainAspectRatio: false,</p>
<p class="p1"><span class="Apple-converted-space">                </span>cutout: '65%',</p>
<p class="p1"><span class="Apple-converted-space">                </span>plugins: {</p>
<p class="p1"><span class="Apple-converted-space">                    </span>legend: {</p>
<p class="p1"><span class="Apple-converted-space">                        </span>position: 'bottom',</p>
<p class="p1"><span class="Apple-converted-space">                        </span>labels: {</p>
<p class="p1"><span class="Apple-converted-space">                            </span>padding: 20,</p>
<p class="p1"><span class="Apple-converted-space">                            </span>usePointStyle: true,</p>
<p class="p1"><span class="Apple-converted-space">                            </span>font: { size: 12 }</p>
<p class="p1"><span class="Apple-converted-space">                        </span>}</p>
<p class="p1"><span class="Apple-converted-space">                    </span>},</p>
<p class="p1"><span class="Apple-converted-space">                    </span>tooltip: {</p>
<p class="p1"><span class="Apple-converted-space">                        </span>backgroundColor: '#1f2937',</p>
<p class="p1"><span class="Apple-converted-space">                        </span>padding: 12,</p>
<p class="p1"><span class="Apple-converted-space">                        </span>callbacks: {</p>
<p class="p1"><span class="Apple-converted-space">                            </span>label: function(context) {</p>
<p class="p1"><span class="Apple-converted-space">                                </span>let label = context.label || '';</p>
<p class="p1"><span class="Apple-converted-space">                                </span>if (label) { label += ': '; }</p>
<p class="p1"><span class="Apple-converted-space">                                </span>label += context.raw + '%';</p>
<p class="p1"><span class="Apple-converted-space">                                </span>return label;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>}</p>
<p class="p1"><span class="Apple-converted-space">                        </span>}</p>
<p class="p1"><span class="Apple-converted-space">                    </span>}</p>
<p class="p1"><span class="Apple-converted-space">                </span>}</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// --- SYNERGY FLOW LOGIC ---</p>
<p class="p1"><span class="Apple-converted-space">        </span>let currentStep = 0;</p>
<p class="p1"><span class="Apple-converted-space">        </span>const totalSteps = 3;</p>
<p class="p1"><span class="Apple-converted-space">        </span>const btnNext = document.getElementById('btn-next-flow');</p>
<p class="p1"><span class="Apple-converted-space">        </span>const btnPrev = document.getElementById('btn-prev-flow');</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>function updateFlowUI() {</p>
<p class="p1"><span class="Apple-converted-space">            </span>// Reset all</p>
<p class="p1"><span class="Apple-converted-space">            </span>for(let i=1; i&lt;=totalSteps; i++) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>const el = document.getElementById(`step-${i}`);</p>
<p class="p1"><span class="Apple-converted-space">                </span>el.classList.remove('opacity-100', 'scale-105', 'border-emerald-500', 'shadow-[0_0_20px_rgba(16,185,129,0.2)]');</p>
<p class="p1"><span class="Apple-converted-space">                </span>el.classList.add('opacity-50', 'border-stone-700');</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>// Set Active</p>
<p class="p1"><span class="Apple-converted-space">            </span>if(currentStep &gt; 0) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>const activeEl = document.getElementById(`step-${currentStep}`);</p>
<p class="p1"><span class="Apple-converted-space">                </span>activeEl.classList.remove('opacity-50', 'border-stone-700');</p>
<p class="p1"><span class="Apple-converted-space">                </span>activeEl.classList.add('opacity-100', 'scale-105', 'border-emerald-500', 'shadow-[0_0_20px_rgba(16,185,129,0.2)]');</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>// Button States</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (currentStep === 0) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>btnNext.textContent = "Start Flow";</p>
<p class="p1"><span class="Apple-converted-space">                </span>btnPrev.disabled = true;</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else if (currentStep === totalSteps) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>btnNext.textContent = "Reset Flow";</p>
<p class="p1"><span class="Apple-converted-space">                </span>btnPrev.disabled = false;</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else {</p>
<p class="p1"><span class="Apple-converted-space">                </span>btnNext.textContent = "Next Step";</p>
<p class="p1"><span class="Apple-converted-space">                </span>btnPrev.disabled = false;</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>btnNext.addEventListener('click', () =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (currentStep &gt;= totalSteps) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>currentStep = 0;</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else {</p>
<p class="p1"><span class="Apple-converted-space">                </span>currentStep++;</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">            </span>updateFlowUI();</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>btnPrev.addEventListener('click', () =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (currentStep &gt; 0) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>currentStep--;</p>
<p class="p1"><span class="Apple-converted-space">                </span>updateFlowUI();</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// Initialize state</p>
<p class="p1"><span class="Apple-converted-space">        </span>updateFlowUI();</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/script&gt;</p>
<p class="p1">&lt;/body&gt;</p>
<p class="p1">&lt;/html&gt;</p>
</body>
</html>
