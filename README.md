<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Family Hawaii Trip 2025</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <!-- Leaflet CSS -->
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY=" crossorigin=""/>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');
        body { font-family: 'Poppins', sans-serif; background-color: #f0fdf4; -webkit-tap-highlight-color: transparent; }
        
        .island-tag { font-size: 0.70rem; font-weight: 700; letter-spacing: 0.05em; text-transform: uppercase; }
        .kauai { color: #15803d; background-color: #dcfce7; }
        .oahu { color: #0369a1; background-color: #e0f2fe; }
        .nap-time { background-color: #faf5ff; border-left: 4px solid #d8b4fe; }

        .details-content { display: none; }
        .details-content.active { display: block; animation: slideDown 0.3s ease-out; }
        @keyframes slideDown { from { opacity: 0; transform: translateY(-5px); } to { opacity: 1; transform: translateY(0); } }

        #map { height: 450px; width: 100%; border-radius: 12px; z-index: 1; }
        .leaflet-popup-content { font-family: 'Poppins', sans-serif; font-size: 12px; }
        
        .flight-link { color: #2563eb; text-decoration: underline; font-weight: 600; }
    </style>
</head>
<body class="text-gray-800 pb-24">

    <!-- Hero Section -->
    <div class="relative bg-teal-600 text-white p-6 shadow-lg rounded-b-3xl mb-6">
        <div class="absolute top-0 right-0 p-4 opacity-20">
            <i class="fa-solid fa-umbrella-beach text-6xl"></i>
        </div>
        <h1 class="text-2xl font-bold mb-1">Aloha, Family! 🌺</h1>
        <p class="text-teal-100 text-xs mb-4">Seattle ➔ Hawaii • Dec 21 - 31</p>
        
        <!-- Navigation Tabs -->
        <div class="flex justify-center gap-2 mt-4 bg-teal-800/30 p-1 rounded-full backdrop-blur-sm">
            <button onclick="switchTab('timeline')" id="btn-timeline" class="tab-btn bg-white text-teal-700 px-4 py-1.5 rounded-full text-xs font-bold shadow transition flex-1">Itinerary</button>
            <button onclick="switchTab('map')" id="btn-map" class="tab-btn text-white px-4 py-1.5 rounded-full text-xs font-bold hover:bg-white/20 transition flex-1">Map</button>
            <button onclick="switchTab('logistics')" id="btn-logistics" class="tab-btn text-white px-4 py-1.5 rounded-full text-xs font-bold hover:bg-white/20 transition flex-1">Info</button>
        </div>
    </div>

    <!-- MAIN CONTAINER -->
    <div class="max-w-md mx-auto px-4" id="main-container">
        
        <!-- TAB 1: LOGISTICS VIEW -->
        <div id="logistics-view" class="view-section hidden space-y-4">
            <!-- Flights -->
            <div class="bg-white p-4 rounded-xl shadow-sm border-l-4 border-blue-500">
                <h3 class="font-bold text-gray-700 mb-3 text-sm flex items-center gap-2"><i class="fa-solid fa-plane text-blue-500"></i> Flights</h3>
                <div class="space-y-3 text-xs">
                    <div class="flex justify-between items-center bg-blue-50 p-2 rounded">
                        <span>Dec 21 • <a href="https://www.google.com/search?q=Delta+DL0351" target="_blank" class="flight-link">DL0351</a><br><span class="text-gray-500">SEA ➔ HNL</span></span>
                        <span class="font-bold text-blue-800">8:25 AM</span>
                    </div>
                    <div class="flex justify-between items-center bg-blue-50 p-2 rounded">
                        <span>Dec 23 • <a href="https://www.google.com/search?q=Alaska+Airlines+AS8279" target="_blank" class="flight-link">AS8279</a><br><span class="text-gray-500">HNL ➔ LIH</span></span>
                        <span class="font-bold text-blue-800">10:45 AM</span>
                    </div>
                    <div class="flex justify-between items-center bg-blue-50 p-2 rounded">
                        <span>Dec 26 • <a href="https://www.google.com/search?q=Alaska+Airlines+AS8315" target="_blank" class="flight-link">AS8315</a><br><span class="text-gray-500">LIH ➔ HNL</span></span>
                        <span class="font-bold text-blue-800">5:40 PM</span>
                    </div>
                    <div class="flex justify-between items-center bg-blue-50 p-2 rounded">
                        <span>Dec 31 • <a href="https://www.google.com/search?q=Delta+DL0352" target="_blank" class="flight-link">DL0352</a><br><span class="text-gray-500">HNL ➔ SEA</span></span>
                        <span class="font-bold text-blue-800">8:10 AM</span>
                    </div>
                </div>
            </div>

            <!-- Car Rental Alert -->
            <div class="bg-white p-4 rounded-xl shadow-sm border-l-4 border-orange-500">
                <h3 class="font-bold text-gray-700 mb-2 text-sm flex items-center gap-2"><i class="fa-solid fa-car text-orange-500"></i> Car Rentals</h3>
                <div class="text-xs space-y-3">
                    <div class="bg-orange-50 p-2 rounded border border-orange-100">
                        <p class="font-bold text-orange-800">Kauai (Airport)</p>
                        <p>Pick: Dec 23 @ 11:30 AM</p>
                        <p>Drop: Dec 24 @ 1:00 PM <span class="text-red-500 font-bold">(1 Day Only!)</span></p>
                    </div>
                    <div class="bg-orange-50 p-2 rounded border border-orange-100">
                        <p class="font-bold text-orange-800">Oahu (City)</p>
                        <p class="mb-1"><i class="fa-solid fa-location-dot"></i> <a href="https://www.google.com/maps/search/?api=1&query=Enterprise+Rent-A-Car+Waikiki+Sunset" target="_blank" class="underline">Enterprise Waikiki Sunset</a></p>
                        <p>Pick: Dec 27</p>
                        <p>Drop: Dec 31</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- TAB 2: MAP VIEW -->
        <div id="map-view" class="view-section hidden">
            <div class="bg-white p-2 rounded-xl shadow-md">
                <div id="map"></div>
                <div class="flex gap-2 mt-2 overflow-x-auto pb-2">
                    <button onclick="panMap('HNL')" class="text-xs bg-blue-100 text-blue-800 px-3 py-1 rounded-full whitespace-nowrap">Oahu</button>
                    <button onclick="panMap('LIH')" class="text-xs bg-green-100 text-green-800 px-3 py-1 rounded-full whitespace-nowrap">Kauai</button>
                    <button onclick="panMap('SEA')" class="text-xs bg-gray-100 text-gray-800 px-3 py-1 rounded-full whitespace-nowrap">Seattle</button>
                </div>
            </div>
        </div>

        <!-- TAB 3: TIMELINE VIEW -->
        <div id="timeline-view" class="view-section space-y-4">
            
            <!-- DAY 1 -->
            <div onclick="toggleDetails('d1')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag oahu px-2 py-0.5 rounded">Oahu</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 21 <span class="text-gray-400 text-sm font-normal">Sun</span></h3>
                        <p class="text-xs text-gray-500">Arrival in Paradise</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d1" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-blue-500"><i class="fa-solid fa-plane-arrival"></i></div>
                        <div>
                            <p class="font-bold">Land HNL (DL0351)</p>
                            <p class="text-xs">12:55 PM</p>
                        </div>
                    </div>
                    <!-- Nap Block -->
                    <div class="flex items-start gap-3 nap-time p-2 rounded">
                        <div class="w-8 text-center text-purple-400"><i class="fa-solid fa-moon"></i></div>
                        <div>
                            <p class="font-bold text-purple-800">Check-in & Toddler Nap 🧸</p>
                            <p class="text-xs text-purple-600">~1:30 PM @ Hyatt Centric Waikiki.</p>
                            <a href="https://www.google.com/maps/search/?api=1&query=Hyatt+Centric+Waikiki+Beach" target="_blank" class="text-blue-600 text-xs mt-1 block hover:underline"><i class="fa-solid fa-map-pin"></i> Open Map</a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- DAY 2 -->
            <div onclick="toggleDetails('d2')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag oahu px-2 py-0.5 rounded">Oahu</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 22 <span class="text-gray-400 text-sm font-normal">Mon</span></h3>
                        <p class="text-xs text-gray-500">Waikiki (No Car)</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d2" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-yellow-500"><i class="fa-solid fa-sun"></i></div>
                        <div>
                            <p class="font-bold">Waikiki Beach Day 🏖️</p>
                            <p class="text-xs">Walkable. Easy food nearby.</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-3 nap-time p-2 rounded">
                        <div class="w-8 text-center text-purple-400"><i class="fa-solid fa-baby"></i></div>
                        <div>
                            <p class="font-bold text-purple-800">Hotel Rest</p>
                            <p class="text-xs text-purple-600">Mid-day break for the little one.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- DAY 3 -->
            <div onclick="toggleDetails('d3')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden border-l-4 border-green-500">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag kauai px-2 py-0.5 rounded">Kauai</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 23 <span class="text-gray-400 text-sm font-normal">Tue</span></h3>
                        <p class="text-xs text-gray-500">To Kauai</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d3" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-blue-500"><i class="fa-solid fa-plane"></i></div>
                        <div>
                            <p class="font-bold">Flight AS8279 (HNL->LIH)</p>
                            <p class="text-xs">10:45 AM - 11:28 AM</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-orange-500"><i class="fa-solid fa-key"></i></div>
                        <div>
                            <p class="font-bold">Pick up Car (Airport)</p>
                            <p class="text-xs text-red-500 font-bold">1 Day Rental Only!</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-green-600"><i class="fa-solid fa-hotel"></i></div>
                        <div>
                            <p class="font-bold">Grand Hyatt Kauai</p>
                            <a href="https://www.google.com/maps/search/?api=1&query=Grand+Hyatt+Kauai+Resort" target="_blank" class="text-blue-600 text-xs mt-1 block hover:underline"><i class="fa-solid fa-map-pin"></i> Open Map</a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- DAY 4 -->
            <div onclick="toggleDetails('d4')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden border-l-4 border-green-500">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag kauai px-2 py-0.5 rounded">Kauai</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 24 <span class="text-gray-400 text-sm font-normal">Wed</span></h3>
                        <p class="text-xs text-gray-500">Return Car</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d4" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-green-700"><i class="fa-solid fa-binoculars"></i></div>
                        <div>
                            <p class="font-bold">Pu’u O Kila Lookout</p>
                            <a href="https://www.google.com/maps/search/?api=1&query=Pu’u+O+Kila+Lookout" target="_blank" class="text-blue-600 text-xs mt-1 block hover:underline"><i class="fa-solid fa-map-pin"></i> Open Map</a>
                        </div>
                    </div>
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-red-500"><i class="fa-solid fa-clock"></i></div>
                        <div>
                            <p class="font-bold">Yang Returns Car (1:00 PM)</p>
                            <p class="text-xs text-red-600 font-bold">Lihue Airport.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- DAY 5 -->
            <div onclick="toggleDetails('d5')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden border-l-4 border-green-500">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag kauai px-2 py-0.5 rounded">Kauai</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 25 <span class="text-gray-400 text-sm font-normal">Thu</span></h3>
                        <p class="text-xs text-gray-500">Christmas 🎄</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d5" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-red-600"><i class="fa-solid fa-gift"></i></div>
                        <div>
                            <p class="font-bold">Resort Day</p>
                            <p class="text-xs">Pools & Relaxation at Grand Hyatt.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- DAY 6 -->
            <div onclick="toggleDetails('d6')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden border-l-4 border-green-500">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag kauai px-2 py-0.5 rounded">Kauai / Oahu</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 26 <span class="text-gray-400 text-sm font-normal">Fri</span></h3>
                        <p class="text-xs text-gray-500">Back to Oahu</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d6" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-blue-500"><i class="fa-solid fa-plane-departure"></i></div>
                        <div>
                            <p class="font-bold">Flight AS8315 (LIH->HNL)</p>
                            <p class="text-xs">5:40 PM - 6:18 PM</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-purple-500"><i class="fa-solid fa-hotel"></i></div>
                        <div>
                            <p class="font-bold">Check-in: Hyatt Place Waikiki</p>
                            <a href="https://www.google.com/maps/search/?api=1&query=Hyatt+Place+Waikiki+Beach" target="_blank" class="text-blue-600 text-xs mt-1 block hover:underline"><i class="fa-solid fa-map-pin"></i> Open Map</a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- OAHU CAR DAYS -->
            <div class="bg-blue-50 p-4 rounded-xl border border-blue-100">
                <div class="flex items-center gap-2 mb-2 justify-center">
                    <i class="fa-solid fa-car-side text-blue-600 text-xl"></i>
                    <h2 class="font-bold text-blue-800">Oahu Car Days</h2>
                </div>
                <div class="bg-white p-2 rounded mb-3 border border-blue-200 text-xs text-center">
                    <p><strong>Pickup:</strong> Dec 27 @ Enterprise Waikiki Sunset</p>
                    <a href="https://www.google.com/maps/search/?api=1&query=Enterprise+Rent-A-Car+Waikiki+Sunset" target="_blank" class="text-blue-600 font-bold underline">Open Location</a>
                </div>
                
                <p class="text-center text-xs text-blue-600 mb-4">Suggested Plan for Requested Spots:</p>
                
                <!-- Day 27 -->
                <div class="bg-white rounded-lg shadow-sm mb-2 p-3">
                    <span class="font-bold text-sm block mb-1">Dec 27: North & Central 🍍</span>
                    <ul class="text-xs text-gray-600 space-y-2">
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Dole+Plantation" target="_blank" class="text-blue-600 hover:underline">1. Dole Plantation</a> (Train ride!)</li>
                    </ul>
                </div>

                <!-- Day 28 -->
                <div class="bg-white rounded-lg shadow-sm mb-2 p-3">
                    <span class="font-bold text-sm block mb-1">Dec 28: History & Town 🏛️</span>
                    <ul class="text-xs text-gray-600 space-y-2">
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Pearl+Harbor+National+Memorial" target="_blank" class="text-blue-600 hover:underline">1. Pearl Harbor Memorial</a> (Morning)</li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Iolani+Palace" target="_blank" class="text-blue-600 hover:underline">2. Iolani Palace</a></li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Nuuanu+Pali+Lookout" target="_blank" class="text-blue-600 hover:underline">3. Nuʻuanu Pali Lookout</a> (Windy!)</li>
                    </ul>
                </div>

                <!-- Day 29 -->
                <div class="bg-white rounded-lg shadow-sm mb-2 p-3">
                    <span class="font-bold text-sm block mb-1">Dec 29: Windward Nature 🌿</span>
                    <ul class="text-xs text-gray-600 space-y-2">
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Hoʻomaluhia+Botanical+Garden" target="_blank" class="text-blue-600 hover:underline">1. Hoʻomaluhia Botanical Garden</a></li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Kailua+Beach+Park" target="_blank" class="text-blue-600 hover:underline">2. Kailua Beach Park</a> (Toddler safe)</li>
                    </ul>
                </div>

                 <!-- Day 30 -->
                 <div class="bg-white rounded-lg shadow-sm p-3">
                    <span class="font-bold text-sm block mb-1">Dec 30: Town Parks 🪁</span>
                    <ul class="text-xs text-gray-600 space-y-2">
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Ala+Moana+Regional+Park" target="_blank" class="text-blue-600 hover:underline">1. Ala Moana Regional Park</a></li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Kapiolani+Regional+Park" target="_blank" class="text-blue-600 hover:underline">2. Kapiʻolani Regional Park</a> (Zoo nearby)</li>
                    </ul>
                </div>
            </div>

            <!-- DAY 31 -->
            <div onclick="toggleDetails('d31')" class="bg-white rounded-xl shadow-sm hover:shadow-md transition cursor-pointer overflow-hidden opacity-90">
                <div class="p-4 border-b border-gray-100 flex justify-between items-center">
                    <div>
                        <span class="island-tag oahu px-2 py-0.5 rounded">Oahu</span>
                        <h3 class="font-bold text-lg text-gray-800">Dec 31 <span class="text-gray-400 text-sm font-normal">Wed</span></h3>
                        <p class="text-xs text-gray-500">Departure</p>
                    </div>
                    <i class="fa-solid fa-chevron-down text-gray-300"></i>
                </div>
                <div id="d31" class="details-content bg-gray-50 p-4 text-sm space-y-3">
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-red-500"><i class="fa-solid fa-car"></i></div>
                        <div>
                            <p class="font-bold">Return Rental Car</p>
                            <p class="text-xs">Drop at Waikiki Sunset. Taxi/Uber to HNL.</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-3">
                        <div class="w-8 text-center text-blue-500"><i class="fa-solid fa-plane"></i></div>
                        <div>
                            <p class="font-bold">Flight DL0352 (HNL -> SEA)</p>
                            <p class="text-xs">8:10 AM</p>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </div>

    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo=" crossorigin=""></script>
    
    <script>
        function switchTab(tabId) {
            document.querySelectorAll('.view-section').forEach(el => el.classList.add('hidden'));
            document.getElementById(tabId + '-view').classList.remove('hidden');
            
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('bg-white', 'text-teal-700', 'shadow');
                btn.classList.add('text-white');
            });
            const activeBtn = document.getElementById('btn-' + tabId);
            activeBtn.classList.remove('text-white');
            activeBtn.classList.add('bg-white', 'text-teal-700', 'shadow');

            if(tabId === 'map') {
                setTimeout(() => { if(window.tripMap) window.tripMap.invalidateSize(); }, 100);
            }
        }

        function toggleDetails(id) {
            const element = document.getElementById(id);
            if (element.classList.contains('active')) {
                element.classList.remove('active');
            } else {
                element.classList.add('active');
            }
        }

        // Map Functions
        var mapLocations = {
            'SEA': [47.4502, -122.3088],
            'HNL': [21.3069, -157.8583],
            'LIH': [21.9813, -159.3712]
        };

        function panMap(loc) {
            if(window.tripMap && mapLocations[loc]) {
                window.tripMap.setView(mapLocations[loc], 11);
            }
        }

        document.addEventListener('DOMContentLoaded', function() {
            // Default center: Honolulu
            var map = L.map('map').setView(mapLocations['HNL'], 11);
            window.tripMap = map;

            // Use Google Maps Tiles (Streets)
            L.tileLayer('http://{s}.google.com/vt/lyrs=m&x={x}&y={y}&z={z}',{
                maxZoom: 20,
                subdomains:['mt0','mt1','mt2','mt3']
            }).addTo(map);

            // Icons
            var iconPlane = L.divIcon({html: '<i class="fa-solid fa-plane text-blue-600 text-xl"></i>', className: 'bg-transparent'});
            var iconHotel = L.divIcon({html: '<i class="fa-solid fa-hotel text-purple-600 text-xl"></i>', className: 'bg-transparent'});
            var iconSpot = L.divIcon({html: '<i class="fa-solid fa-location-dot text-red-500 text-xl"></i>', className: 'bg-transparent'});

            // Markers
            // Hotels
            L.marker([21.2798, -157.8258], {icon: iconHotel}).addTo(map).bindPopup("Hyatt Waikiki");
            L.marker([21.8753, -159.4398], {icon: iconHotel}).addTo(map).bindPopup("Grand Hyatt Kauai");
            
            // POIs
            L.marker([21.5262, -158.0378], {icon: iconSpot}).addTo(map).bindPopup("Dole Plantation");
            L.marker([21.3649, -157.9495], {icon: iconSpot}).addTo(map).bindPopup("Pearl Harbor");
            L.marker([21.3069, -157.8591], {icon: iconSpot}).addTo(map).bindPopup("Iolani Palace");
            L.marker([21.3855, -157.8093], {icon: iconSpot}).addTo(map).bindPopup("Ho'omaluhia Bot. Garden");
            L.marker([21.3989, -157.7289], {icon: iconSpot}).addTo(map).bindPopup("Kailua Beach");
            L.marker([21.3662, -157.7932], {icon: iconSpot}).addTo(map).bindPopup("Nu'uanu Pali Lookout");
            L.marker([21.2917, -157.8485], {icon: iconSpot}).addTo(map).bindPopup("Ala Moana Park");
            L.marker([21.2686, -157.8189], {icon: iconSpot}).addTo(map).bindPopup("Kapi'olani Park");

        });
    </script>
</body>
</html>
