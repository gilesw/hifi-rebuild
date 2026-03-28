graph TD
    subgraph SOURCES["1. SOURCES"]
        PC[Linux PC <br/> Streaming / Kodi]
    end

    subgraph BRAINS["2. THE BRAIN (MARANTZ AV 30)"]
        DAC[Denafrips Pontus 15th <br/> R-2R DAC]
        AVP[MARANTZ AV 30 <br/> 11.4 CH Processor]
        
        PC -- USB --> DAC
        DAC -- "XLR (Pure Analog)" --> AVP
        PC -- HDMI --> AVP
    end

    subgraph AMPS["3. AMPLIFICATION (NORD / NCORE)"]
        Nord3[NORD 3-CH AMP <br/> Front L/C/R]
        NCore[2x NCORE MONOS <br/> Surrounds]
        Sub[REL ACTIVE SUB]

        %% Main Audio Connections
        AVP -- "XLR Out (Front L/R)" --> Nord3
        AVP -- "XLR Out (Center)" --> Nord3
        AVP -- "XLR Out (Surrounds)" --> NCore
        AVP -- "LFE Out" --> Sub
    end

    subgraph SPEAKERS["4. SPEAKERS"]
        RibbonLR[Ribbon Towers]
        RibbonC[Ribbon Center]
        Rears[Surround Speakers]
        
        Nord3 -- Wire --> RibbonLR
        Nord3 -- Wire --> RibbonC
        NCore -- Wire --> Rears
    end

    %% Trigger Logic
    AVP -.->|Trigger 1| Nord3
    AVP -.->|Trigger 2| NCore

    style AVP fill:#ccf,stroke:#333,stroke-width:2px
    style DAC fill:#f9f,stroke:#333
