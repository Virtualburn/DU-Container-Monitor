<p># <strong>DU-CONTAINER_MONITOR v2.2</strong> #</p>
<p><img src="https://github.com/Virtualburn/DU-Container-Monitor/raw/d6145a48c606952b5d7f70edbf7e5ded9dbf6e9d/HUB_MONITOR.png" width="742" height="371" /></p>
<p><strong>:: OVERVIEW<br /></strong><br />Dual Universe container monitor script for Ores and Pures using various sized containers (from Basic to Advanced Optimized) using singulat container or multiple via hub with <strong>no need to link</strong> as it uses naming system via Core.</p>
<p>This HUD is designed to be used on 2 x Transparent L Screens</p>
<p>This code is destined to Dual Universe game.<br /> This is a Container monitor for pure and ore materials. It can be used to monitor container percentages and it readouts. It was design to have a Container Hub element side each item.<br /> <br /> This HUD was designed for a Large Transparent Screen(or two). Each screen can gather 20 materials. It uses a Zone detector to turn up every board for optimal CPU usage.<br /> <br /><strong>:: INSTRUCTIONS</strong></p>
<ul>
<li data-start="702" data-end="744">Connect a <strong data-start="712" data-end="720">Core</strong> to the PB (any core).</li>
<li data-start="747" data-end="809">Connect <strong data-start="755" data-end="767">SCREEN_A</strong> (required) and optionally <strong data-start="794" data-end="806">SCREEN_B</strong>.</li>
<li data-start="812" data-end="889">(Optional) Connect a <strong data-start="833" data-end="845">Databank</strong> (for storing user vars between sessions).</li>
<li data-start="892" data-end="963">(Optional) Connect <strong data-start="911" data-end="920">DOOR1</strong>/<strong data-start="921" data-end="930">DOOR2</strong> if you want the auto-door bit.</li>
<li data-start="966" data-end="1045">Name the hub/containers as before (e.g., <code data-start="1007" data-end="1023">CH_XXL_BAUXITE</code>, <code data-start="1025" data-end="1037">C_XLu_COAL</code>, etc.).<br /><br /></li>
</ul>
<p><img src="https://github.com/Virtualburn/DU-Container-Monitor/raw/d6145a48c606952b5d7f70edbf7e5ded9dbf6e9d/SLOTS.png" width="229" height="337" /></p>
<p><strong>NOTE</strong>: When you have pasted the code it will rename the Slots automatically - if you are using a second screen rename the last slot to SCREEN_B.</p>
<ul>
<li>Check parameters 'Advanced &gt; Edit Lua parameters'</li>
</ul>
<p>&nbsp;</p>
<p><img src="https://github.com/Virtualburn/DU-Container-Monitor/raw/d6145a48c606952b5d7f70edbf7e5ded9dbf6e9d/USER_VARS.png" width="512" height="532" /></p>
<ul>
<li>Label Containers and/or hubs - see below</li>
</ul>
<p><strong>:: EXTRA</strong></p>
<ul>
<li>Link a relay to the board and the screens and detector zone to the relay to activate when you are present.</li>
</ul>
<p><br /><strong>:: LABELLING INSTRUCTIONS (example)<br /></strong><br /> CH stands for ContainerHub<br /> C stands for Container<br />2 for quantity of containers<br /> L for size of the container<br /> ACANTHITE for material type<br /> <br />CH_2L_ACANTHITE</p>
<p>::&nbsp;EXTRA MATERIALS<br /><br />"OXYGEN", "HYDROGEN", "WARPCELL"<br /> <br />::&nbsp;<strong>DOORS<br /></strong><br /> Link them to the board. Name the slots DOOR1 and DOOR2 (optional).<br /> Activate at parameters (UseDoors)<br />Edit the caracter names that will trigger the doors (final function at System/start)<br /> <br /> <strong>CHANGE LOG: DU-CONTAINER-MONITOR</strong></p>
<p data-start="4637" data-end="4658"><strong data-start="4637" data-end="4658">v2.2 &mdash; 2025-09-07</strong></p>
<ul>
<li data-start="4661" data-end="4770">-- Added <strong data-start="4667" data-end="4704">capacity talents (0&ndash;5, +10% each)</strong> with per-size <strong data-start="4719" data-end="4738">base capacities</strong>; removed per-tier hardcoding.</li>
<li data-start="4773" data-end="4837">-- Implemented <strong data-start="4785" data-end="4809">tier step multiplier</strong> (+30% per step: c&rarr;u&rarr;a&rarr;r).</li>
<li data-start="4840" data-end="4930">-- Added <strong data-start="4846" data-end="4888">mass-reduction talents (0&ndash;5, &minus;5% each)</strong> correction when converting mass&rarr;volume.</li>
<li data-start="4933" data-end="5001">-- Hardened <strong data-start="4942" data-end="4962">size/tier parser</strong> to avoid <code data-start="4972" data-end="4980">XL/XXL</code> collapsing to <code data-start="4995" data-end="4998">L</code>.</li>
<li data-start="5004" data-end="5091">-- Reworked <strong data-start="5013" data-end="5032">Databank schema</strong> to store only talents, tier step %, and base capacities.</li>
<li data-start="5094" data-end="5144">-- Fixed <strong data-start="5100" data-end="5113">DoorUsers</strong> variable case; minor CSS typo.</li>
</ul>
<p data-start="5146" data-end="5154"><strong data-start="5146" data-end="5154">v2.1</strong></p>
<ul>
<li data-start="5157" data-end="5228">-- Initial integration of <strong>XL/XXL</strong> sizes and <strong>uncommon/advanced/rare</strong> tiers.</li>
<li data-start="5231" data-end="5286">-- First pass of mass&rarr;<strong>volume and capacity</strong> display updates.</li>
</ul>
<p><strong>v2.0</strong></p>
<ul>
<li>-- Parse tokens like "10XLu", "2XXLa", "5L", "xxl", "XL-", "XXL " etc. For new container sizes and tiers</li>
<li>--&nbsp;<code data-start="3024" data-end="3040">CH_XXL_BAUXITE</code> (count defaults to <code data-start="3061" data-end="3064">1</code>)</li>
<li>-- Name check for invalid characters and/or spaces</li>
<li>-- Improved container size parsing to incorporate new sizes</li>
<li>-- Corrected: liters = (container mass of contents) / (material density)</li>
<li>-- Added USER VAR to accomodate talents 1 - 5 (5% to 25% Mass reduction)</li>
<li>-- Added USER VAR to accomodate talents 1 - 5 (10% - 50% Capacity Increase)</li>
<li>-- Replaced placeholders with standard set USER VAR forbase capacity (to support MyDU server changes)</li>
</ul>
<p><strong>Future updates: </strong></p>
<ul>
<li>-- Add option to easily add different variants of containers</li>
<li>-- Add Exotic Containers and others as this focuses on 'Advanced Optimized' for static cores</li>
</ul>
<p>~</p>
<p>v1.4 11 Nov 2020 -&nbsp;v1.9 01 Dec 2020 ~ Please see original repo:&nbsp;<a href="https://github.com/carmopereira/DU-Container-Monitor" target="_blank" rel="noopener">/carmopereira/DU-Container-Monitor</a></p>
<p>~</p>
<p><strong>Bonus Screen</strong></p>
<p>30_HUB_SCREEN_L_HTML</p>
<p>Simple HTML paste direct to Screen L and will host 30 x Container hubs.</p>
<p><img src="https://github.com/Virtualburn/DU-Container-Monitor/raw/fa5a4da293662ff4f9bdd7aa0594045cf16a0610/30_HUB_SCREEN.png" width="700" height="631" /><br />This is a HTML only board.</p>
