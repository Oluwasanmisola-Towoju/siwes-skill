# Theory linkage bank — 200L Computer Engineering

Use these pre-built sentences to connect practical SIWES activities to Computer Engineering
engineering principles. Insert the most relevant sentence at the end of each major activity
section in the Training Report, and use them to build the theory-linkage table in Chapter 4.
Adapt the wording naturally to fit the context; never paste verbatim if it does not fit.

The organisation here is by engineering concept area, not by course code. Pick the area that
matches the activity.

---

## Electric circuits and power fundamentals

- "Tracing the power fault required applying Kirchhoff's Voltage Law: the sum of all
  voltage drops around any closed loop equals the supply voltage. I measured the drop at
  each component in sequence and identified the failed load by the voltage that did not add up."
- "The UPS sizing calculation connected directly to the principle of real power and apparent
  power: the difference between watts and volt-amperes explained why the 600 VA UPS could
  not sustain a 550 W server load for the rated backup duration."
- "Understanding why the long cable run to the server room caused voltage sag required
  applying Ohm's law to cable resistance: with 15 metres of 1.5 mm² copper at 0.013 Ω/m,
  the estimated resistance was about 0.4 Ω, producing a noticeable drop at full load."

---

## Digital logic and number systems

- "Converting IP address allocations between binary and decimal during subnet planning
  reinforced the positional-value representation of binary numbers, showing that an
  address is not arbitrary but encodes network and host fields in specific bit positions."
- "The VLAN configuration required understanding logical switching at the data-link layer,
  where each frame carries an 802.1Q tag that switches use to segment traffic without
  physically separating cables — a direct application of Boolean address filtering."
- "Debugging the microcontroller's output required reading the register map in the datasheet,
  which stores device state as individual bits. Setting or clearing a single bit with a
  bitwise OR or AND mask is the practical form of the bitwise logic covered in digital circuits."

---

## Computer architecture and systems

- "Profiling the application's slow response revealed that repeated small reads from the
  hard disk were the bottleneck. This connected to the memory hierarchy concept: accessing
  DRAM is orders of magnitude faster than disk I/O, and restructuring the code to buffer
  reads in memory reduced the response time substantially."
- "Analysing the CPU load during batch processing reinforced pipelining principles: the
  processor overlaps fetch, decode and execute stages, so a loop with many independent
  operations runs faster than one where each step depends on the previous."
- "Understanding why the server slowed under concurrent requests connected to the idea of
  process scheduling: the operating system time-slices between threads, and too many threads
  chasing the same shared resource creates contention that no amount of CPU power resolves."

---

## Algorithms and data structures

- "Optimising the database query layer required applying algorithmic complexity analysis.
  The original nested loop ran in O(n²) time; replacing the inner loop with a hash-map
  lookup reduced the average case to O(1) and made the difference visible at scale."
- "The routing algorithm I helped document used a shortest-path calculation. The principle —
  that finding the minimum-cost path through a graph requires visiting every reachable node
  in order of accumulated cost — is the same whether the graph is a road network or an IP
  topology."
- "Sorting the asset inventory by department and then by date demonstrated that choosing the
  right sort algorithm matters even at small scale: the built-in Timsort handled real-world
  nearly-sorted data far faster than a naive bubble sort on the same list."

---

## Programming and software fundamentals

- "Structuring the script with separate functions for input validation, processing and output
  applied the single-responsibility principle: each function does one thing, which made it
  straightforward to test and to change one part without breaking the others."
- "Writing the data migration script required understanding how the program controlled execution
  flow: conditional checks prevented the script from overwriting records that already existed,
  which is the same guard pattern that database transactions use to enforce atomicity."
- "Reviewing the existing codebase showed the value of abstraction: the code called a function
  by name without caring how it was implemented, so the team had replaced one database driver
  with a faster one without touching a single line in the rest of the application."

---

## Data communications and networking

- "Configuring static routes required understanding how a router uses the network portion of
  an IP address to decide where to forward a packet. A /26 prefix leaves 6 host bits, giving
  62 usable addresses per subnet — enough for the 40 POS terminals in the shop, with room
  to add devices later."
- "Diagnosing the intermittent packet loss involved checking at each layer of the OSI model:
  the physical cable tested clean, the switch port showed no error counters, and the fault
  was eventually found at the network layer as a duplicate static route entry."
- "The REST API integration demonstrated the client-server model in practice: the client
  sends a stateless HTTP request with all the context the server needs, the server processes
  it independently, and returns a response. Neither side remembers the other between requests."

---

## Operating systems and server administration

- "Configuring file permissions on the Linux server applied the Unix security model: every
  file has an owner, a group and a set of read/write/execute bits for each. Setting the
  wrong group permission had locked the application out of its own log directory."
- "Diagnosing the memory issue required reading the process table and observing how the
  OS allocates heap to each running process. The leak appeared as a process whose resident
  set size grew steadily over time, pointing to memory being allocated but never freed."
- "Automating the backup with a cron job demonstrated how the operating system's scheduler
  triggers processes: the job ran as a subprocess owned by the service account, with its own
  environment, separate from the interactive shell."

---

## Microcontrollers and embedded systems

- "Programming the GPIO pins required writing directly to memory-mapped registers at known
  addresses — the same mechanism the hardware reference manual describes as the connection
  between software and silicon. Setting a specific bit in the control register configured
  the pin as an output; clearing it switched it to an input."
- "Implementing the sensor polling loop with a timer interrupt rather than a busy-wait loop
  applied the principle of interrupt-driven design: the processor does other work between
  readings instead of spinning in a loop, which reduces power consumption and allows
  concurrent tasks."
- "Interfacing the I2C sensor required understanding the master-slave protocol: the master
  generates the clock and initiates every transaction, the slave responds to its address.
  Getting the timing right required consulting the datasheet for the minimum hold times."

---

## Signals and signal processing

- "The audio capture pipeline required choosing a sampling rate. The Nyquist-Shannon theorem
  states that a signal must be sampled at more than twice its highest frequency component to
  be reconstructed without aliasing; for voice up to 8 kHz, sampling at 16 kHz was the
  minimum safe rate."
- "Analysing the sensor output in the frequency domain revealed a 50 Hz noise component from
  the power supply. Applying a simple low-pass filter with a cutoff below 50 Hz removed it,
  which connected the work to the concept of filter frequency response and stopband attenuation."

---

## Semiconductor devices and basic electronics

- "Testing the transistor switch in the relay driver circuit applied the principle that a
  BJT in saturation behaves like a closed switch: with enough base current, the collector-to-
  emitter voltage drops to near zero, allowing the full supply voltage to appear across the relay coil."
- "Inspecting the failed power supply board showed a bulged electrolytic capacitor. The role
  of that capacitor — smoothing the rectified DC by charging during peaks and discharging
  into the load between peaks — explains why its failure caused the ripple voltage to exceed
  the regulator's input tolerance."

---

## General-purpose linkages (use when the specific area is not listed above)

- "This practical experience reinforced the principle that academic models are not abstract
  constructs but are directly encoded in the systems and tools used by professional engineering
  teams. Seeing the theory at work in a real fault made the underlying mechanism clearer than
  any classroom exercise had."
- "The gap between textbook descriptions and industrial practice was narrower than I had
  expected. The concepts that previously existed as equations and diagrams became concrete
  constraints and design decisions that directly shaped the quality of the work."
- "The problem-solving approach the team used — observe the symptom, form a hypothesis,
  test it with the minimum intervention needed, then revise — is the same method the
  Computer Engineering programme builds across every practical course."
