<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>ISO 23247 – Digital Twin Framework</title>

<style>
/* =====================================================
   RESET E BASE GLOBAL
===================================================== */

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background: #F2F2F2;
}


/* =====================================================
   WRAPPERS BASE
===================================================== */

.iso-wrapper,
.core-wrapper,
.core-grid-wrapper,
.ome-wrapper,
.user-twin-wrapper,
.device-twin-wrapper {
    position: relative;
}

.main-stack {
    display: flex;
    flex-direction: column;
    gap: 20px;
    position: relative;
}


/* =====================================================
   GRID PRINCIPAL ISO
===================================================== */

.iso-grid {
    position: relative;
    display: grid;
    grid-template-columns: 1fr 180px;
    grid-template-rows: auto auto;
    gap: 20px;
    padding: 20px;
    align-items: start;
    z-index: 1;
}


/* =====================================================
   COLUNA DE CONTEÚDO
===================================================== */

.content {
    display: flex;
    flex-direction: column;
    gap: 40px;
    position: relative;
    z-index: 1;
}


/* =====================================================
   ENTIDADES
===================================================== */

.entity {
    border: 3px solid #727A85;
    background: #E2EEFF;
    padding: 16px;
}

.entity-title {
    font-size: 20px;
    font-weight: bold;
    text-align: center;
    margin-bottom: 16px;
}


/* =====================================================
   CORE GRID (DIGITAL TWIN)
===================================================== */

.core-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.sub-entity {
    border: 2px solid #727A85;
    background: #E2EEFF;
    padding: 12px;
    position: relative;
    z-index: 2;
}

.sub-title {
    font-size: 14px;
    font-weight: bold;
    text-align: center;
    margin-bottom: 10px;
}


/* =====================================================
   LINHAS DO CORE
===================================================== */

.core-line-straight {
    position: absolute;
    top: 50%;
    left: 16px;
    right: 16px;
    height: 2px;
    background: #727A85;
    z-index: 0;
}

.u-line-left {
    position: absolute;
    left: calc(16.66% + 10px);
    top: 50%;
    width: 2px;
    height: 15px;
    background: #727A85;
    transform: translateY(-100%);
    z-index: 0;
}

.u-line-top {
    position: absolute;
    left: calc(16.66% + 10px);
    right: calc(16.66% + 10px);
    top: calc(50% - 15px);
    height: 1px;
    background: #727A85;
    z-index: 0;
}

.u-line-right {
    position: absolute;
    right: calc(16.66% + 10px);
    top: calc(50% - 15px);
    width: 2px;
    height: 40px;
    background: #727A85;
    z-index: 0;
}


/* =====================================================
   FUNCTIONAL ENTITIES (FE)
===================================================== */

.fe {
    background: #ffffff;
    border: 1.5px solid #727A85;
    padding: 16px 12px;
    margin-bottom: 8px;
    text-align: center;
    font-size: 12px;
    cursor: pointer;
}

.fe-twin {
    background: #ffffff;
    border: 1.5px solid #727A85;
    padding: 8px;
    margin-bottom: 8px;
    min-height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 12px;
    cursor: pointer;
}

.fe:hover {
    background: #e8f5e9;
}

.fe-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
}

.fe-grid-3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
}


/* =====================================================
   DEVICE COMMUNICATION
===================================================== */

.device-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}


/* =====================================================
   CROSS-SYSTEM ENTITY (SENSÍVEL)
===================================================== */

.cross-column-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    height: 100%;
    gap: 0px;
    align-self: stretch;
}

.cross-column {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
    align-self: stretch;
    border: 3px solid #727A85;
    background: #E2EEFF;
    padding: 10px;
}

.cross-title-vertical {
    writing-mode: vertical-rl;
    transform: rotate(180deg);
    font-weight: bold;
    font-size: 20px;
    white-space: nowrap;
}

.cross-fe-container {
    display: flex;
    gap: 6px;
    height: 100%;
    align-items: stretch;
    flex: 1;
}

.cross-fe-vertical {
    width: 42px;
    flex: 1;
    border: 1.8px solid #727A85;
    background: #ffffff;
    display: flex;
    align-items: center;
    justify-content: center;
    writing-mode: vertical-rl;
    transform: rotate(180deg);
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s;
}

.cross-fe-vertical:hover {
    background: #e8f5e9;
}


/* =====================================================
   LINHAS DE CONEXÃO
===================================================== */

.user-cross-wrapper,
.twin-cross-wrapper,
.device-cross-wrapper {
    position: relative;
}

.line-layer {
    position: absolute;
    inset: 0;
    pointer-events: none;
    z-index: 0;
}

.line {
    position: absolute;
    background: #727A85;
}

.line.h {
    height: 2px;
    top: 50%;
    transform: translateY(-50%);
}

.line.v {
    width: 2px;
}

.user-to-cross {
    left: 100%;
    width: 15px;
}

.twin-to-cross {
    left: 100%;
    width: 15px;
}

.device-to-cross {
    left: 100%;
    width: 15px;
}

.user-to-twin,
.device-to-twin,
.ome-to-device {
    position: absolute;
    left: 50%;
    height: 20px;
    top: -20px;
}


/* =====================================================
   OME
===================================================== */

.ome {
    border: 3px solid #727A85;
    background: #eeeeee;
    padding: 20px;
    text-align: center;
    font-size: 14px;
}


/* =====================================================
   PAINEL DE REQUISITOS
===================================================== */

.requirements-panel {
    position: fixed;
    top: 0;
    right: -420px;
    width: 420px;
    height: 100vh;
    background: white;
    box-shadow: -5px 0 15px rgba(0,0,0,0.3);
    transition: right 0.3s ease;
    z-index: 1000;
    overflow-y: auto;
}

.requirements-panel.open {
    right: 0;
}

.requirements-header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 20px;
    position: sticky;
    top: 0;
    z-index: 10;
}

.requirements-header h3 {
    margin: 0;
    font-size: 16px;
}

.close-btn {
    position: absolute;
    top: 15px;
    right: 15px;
    background: rgba(255,255,255,0.2);
    border: none;
    color: white;
    font-size: 24px;
    cursor: pointer;
    width: 35px;
    height: 35px;
    border-radius: 50%;
}

.close-btn:hover {
    background: rgba(255,255,255,0.3);
}

.requirements-content {
    padding: 20px;
}

.requirement-item {
    background: #f8f9fa;
    padding: 15px;
    margin-bottom: 12px;
    border-radius: 8px;
    border-left: 4px solid #667eea;
}

.requirement-id {
    font-weight: bold;
    color: #667eea;
    margin-bottom: 6px;
}

.requirement-description {
    font-size: 14px;
    color: #495057;
    line-height: 1.5;
}

.requirement-type {
    display: inline-block;
    padding: 2px 8px;
    margin-bottom: 6px;
    border-radius: 12px;
    font-size: 12px;
    font-weight: bold;
    color: white;
    text-transform: uppercase;
}

.requirement-type.functional {
    background-color: #4caf50;
}

.requirement-type.non-functional {
    background-color: #f44336;
}


/* =====================================================
   RESPONSIVO
===================================================== */

@media (max-width: 720px) {

    .iso-grid {
        display: block;
    }

    .cross-column-wrapper {
        position: static;
        margin: 20px 0;
    }

    .cross-column {
        height: auto;
        width: 100%;
    }

    .cross-fe-container {
        flex-direction: row;
        justify-content: center;
    }

    .cross-fe-vertical,
    .cross-title-vertical {
        writing-mode: horizontal-tb;
        transform: none;
        height: auto;
        width: auto;
    }

    .ome-wrapper {
        margin-top: 10px;
    }

    .line,
    .line-layer,
    .cross-lines {
        display: none;
    }
}

</style>
</head>

<body>
    <div class="iso-wrapper">

    <!-- LAYER FOR CONNECTION LINES -->
    <div class="line-layer"></div>

    <div class="iso-grid">

        <!-- =========================================================
             MAIN CONTENT (LEFT SIDE)
        ========================================================== -->
        <div class="content" style="grid-row: 1; grid-column: 1;">
            <div class="main-stack">

                <!-- ================= USER ENTITY ================= -->
                <div class="user-cross-wrapper">
                    <div class="line h user-to-cross"></div>

                    <div class="entity">
                        <div class="entity-title">User Entity</div>
                        <div class="fe">User Interface FE</div>
                    </div>
                </div>

                <!-- ================= DIGITAL TWIN ENTITY ================= -->
                <div class="twin-cross-wrapper">
                    <div class="line h twin-to-cross"></div>

                    <div class="user-twin-wrapper">
                        <div class="line v user-to-twin"></div>

                        <div class="entity">
                            <div class="entity-title">Digital Twin Entity</div>

                            <!-- Core U-shape connectors -->
                            <div class="core-wrapper">
                                <div class="u-line-left"></div>
                                <div class="u-line-top"></div>
                                <div class="u-line-right"></div>
                            </div>

                            <div class="core-grid-wrapper">
                                <div class="core-line-straight"></div>

                                <div class="core-grid">

                                    <!-- Operation and Management Sub-Entity -->
                                    <div class="sub-entity sub-operation">
                                        <div class="sub-title">
                                            Operation and Management <br>
                                            Sub-Entity
                                        </div>

                                        <div class="fe-grid">
                                            <div class="fe-twin" onclick="openPanel('Digital Representation FE')">
                                                Digital Representation FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Maintenance FE')">
                                                Maintenance FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Presentation FE')">
                                                Presentation FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Synchronization FE')">
                                                Synchronization FE
                                            </div>
                                        </div>
                                    </div>

                                    <!-- Application and Service Sub-Entity -->
                                    <div class="sub-entity sub-application">
                                        <div class="sub-title">
                                            Application and Service <br>
                                            Sub-Entity
                                        </div>

                                        <div class="fe-grid">
                                            <div class="fe-twin" onclick="openPanel('Simulation FE')">
                                                Simulation FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Reporting FE')">
                                                Reporting FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Analytic Service FE')">
                                                Analytic Service FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Application Support FE')">
                                                Application Support FE
                                            </div>
                                        </div>
                                    </div>

                                    <!-- Resource Access and Interchange Sub-Entity -->
                                    <div class="sub-entity sub-resource">
                                        <div class="sub-title">
                                            Resource Access and Interchange <br>
                                            Sub-Entity
                                        </div>

                                        <div class="fe-grid">
                                            <div class="fe-twin" onclick="openPanel('Interoperability Support FE')">
                                                Interoperability Support FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Plug and Play Support FE')">
                                                Plug and Play Support FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Access Control FE')">
                                                Access Control FE
                                            </div>
                                            <div class="fe-twin" onclick="openPanel('Peer Interface FE')">
                                                Peer Interface FE
                                            </div>
                                        </div>
                                    </div>

                                </div> <!-- END CORE GRID -->
                            </div>
                        </div>
                    </div>
                </div>

                <!-- ================= DEVICE COMMUNICATION ENTITY ================= -->
                <div class="device-cross-wrapper">
                    <div class="line h device-to-cross"></div>

                    <div class="device-twin-wrapper">
                        <div class="line v device-to-twin"></div>

                        <div class="entity">
                            <div class="entity-title">Device Communication Entity</div>

                            <div class="device-grid">

                                <!-- Data Collection Sub-Entity -->
                                <div class="sub-entity">
                                    <div class="sub-title">Data Collection Sub-Entity</div>

                                    <div class="fe-grid fe-grid-3">
                                        <div class="fe-twin" onclick="openPanel('Data Collecting FE')">
                                            Data Collecting FE
                                        </div>
                                        <div class="fe-twin" onclick="openPanel('Data Pre-Processing FE')">
                                            Data Pre-Processing FE
                                        </div>
                                        <div class="fe-twin" onclick="openPanel('Collection Identification FE')">
                                            Collection Identification FE
                                        </div>
                                    </div>
                                </div>

                                <!-- Device Control Sub-Entity -->
                                <div class="sub-entity">
                                    <div class="sub-title">Device Control Sub-Entity</div>

                                    <div class="fe-grid fe-grid-3">
                                        <div class="fe-twin" onclick="openPanel('Controlling FE')">
                                            Controlling FE
                                        </div>
                                        <div class="fe-twin" onclick="openPanel('Actuation FE')">
                                            Actuation FE
                                        </div>
                                        <div class="fe-twin" onclick="openPanel('Control Identification FE')">
                                            Control Identification FE
                                        </div>
                                    </div>
                                </div>

                            </div>
                        </div>
                    </div>
                </div>

            </div> <!-- END MAIN STACK -->
        </div> <!-- END CONTENT -->

        <!-- ================= OME ENTITY ================= -->
        <div class="ome-wrapper" style="grid-row: 2; grid-column: 1;">
            <div class="line v ome-to-device"></div>

            <div class="ome">
                Observable Manufacturing Elements (OMEs)
                <br><br>

                <div class="fe" onclick="openPanel('Resource-specific FEs')">
                    Resource-specific FEs
                </div>
            </div>
        </div>

        <!-- ================= CROSS-SYSTEM ENTITY ================= -->
        <div class="cross-column-wrapper" style="grid-row: 1; grid-column: 2;">

            <div class="cross-column">
                <div class="cross-fe-container">

                    <div class="cross-fe-vertical" onclick="openPanel('Data Assurance FE')">
                        Data Assurance FE
                    </div>

                    <div class="cross-fe-vertical" onclick="openPanel('Data Translation FE')">
                        Data Translation FE
                    </div>

                    <div class="cross-fe-vertical" onclick="openPanel('Security Support FE')">
                        Security Support FE
                    </div>

                </div>
            </div>

            <div class="cross-title-vertical">
                Cross-System Entity
            </div>

        </div>

    </div> <!-- END ISO GRID -->
</div> <!-- END ISO WRAPPER -->

<!-- =========================================================
     REQUIREMENTS PANEL
========================================================== -->
<div class="requirements-panel" id="panel">
    <div class="requirements-header">
        <h3 id="panel-title">Requirements</h3>
        <button class="close-btn" onclick="closePanel()">×</button>
    </div>

    <div class="requirements-content" id="panel-content"></div>
</div>
</body>
<script>
    /* =========================================================
       REQUIREMENTS MAP
       Mapping of requirements per Functional Entity (FE)
    ========================================================== */
    const requirementsMap = {

        "User Interface FE": [
            {
                id: "REQ-UI-001",
                type: "functional",
                description: "The UI shall provide a responsive dashboard for real-time data."
            },
            {
                id: "REQ-UI-002",
                type: "non-functional",
                description: "UI load time must be under 2 seconds for standard use cases."
            }
        ],

        "Digital Representation FE": [
            {
                id: "REQ-DR-001",
                type: "functional",
                description: "Maintain a digital representation of physical assets."
            },
            {
                id: "REQ-DR-002",
                type: "non-functional",
                description: "Representation updates must occur every 5 seconds."
            }
        ],

        "Maintenance FE": [
            {
                id: "REQ-MA-001",
                type: "functional",
                description: "System shall provide predictive maintenance alerts."
            },
            {
                id: "REQ-MA-002",
                type: "non-functional",
                description: "Maintenance processing latency must be < 1 second."
            }
        ],

        "Simulation FE": [
            {
                id: "REQ-SI-001",
                type: "functional",
                description: "Provide simulation models of manufacturing systems."
            },
            {
                id: "REQ-SI-002",
                type: "non-functional",
                description: "Support what-if analysis based on digital twin data."
            }
        ],

        "Data Collecting FE": [
            {
                id: "REQ-DC-001",
                type: "functional",
                description: "Collect real-time sensor data from devices."
            },
            {
                id: "REQ-DC-002",
                type: "non-functional",
                description: "Data collection latency must be < 100ms."
            }
        ],

        "Data Pre-Processing FE": [
            {
                id: "REQ-DP-001",
                type: "functional",
                description: "Pre-process raw data to remove noise and errors."
            },
            {
                id: "REQ-DP-002",
                type: "non-functional",
                description: "Processing throughput must handle 10,000 events/sec."
            }
        ],

        "Controlling FE": [
            {
                id: "REQ-CO-001",
                type: "functional",
                description: "Control devices based on digital twin instructions."
            }
        ],

        "Actuation FE": [
            {
                id: "REQ-AC-001",
                type: "functional",
                description: "Trigger actuators within 50ms of control command."
            }
        ],

        "Data Assurance FE": [
            {
                id: "REQ-DA-001",
                type: "functional",
                description: "Ensure data integrity and consistency across systems."
            }
        ],

        "Data Translation FE": [
            {
                id: "REQ-DT-001",
                type: "functional",
                description: "Translate data formats between systems."
            }
        ],

        "Security Support FE": [
            {
                id: "REQ-SS-001",
                type: "non-functional",
                description: "All communications must comply with ISO 27001 standards."
            }
        ],

        "Resource-specific FEs": [
            {
                id: "",
                type: "",
                description: "Sem requisitos cadastrados"
            }
        ]
    };

    /* =========================================================
       PANEL ELEMENT REFERENCES
    ========================================================== */
    const panel = document.getElementById("panel");
    const panelTitle = document.getElementById("panel-title");
    const panelContent = document.getElementById("panel-content");

    /* =========================================================
       OPEN REQUIREMENTS PANEL
       Displays requirements associated with a selected FE
    ========================================================== */
    const openPanel = (feName) => {

        const requirements = requirementsMap[feName] || [];

        panelTitle.textContent = `${feName} (${requirements.length})`;

        panelContent.innerHTML = requirements
            .map(req => `
                <div class="requirement-item">
                    <div class="requirement-id">${req.id}</div>
                    <div class="requirement-type ${req.type}">
                        ${req.type.toUpperCase()}
                    </div>
                    <div class="requirement-description">
                        ${req.description}
                    </div>
                </div>
            `)
            .join("");

        panel.classList.add("open");
    };

    /* =========================================================
       CLOSE REQUIREMENTS PANEL
    ========================================================== */
    const closePanel = () => {
        panel.classList.remove("open");
    };

    /* =========================================================
       EVENT DELEGATION
       Handles clicks on all FE elements
    ========================================================== */
    document.body.addEventListener("click", (event) => {

        const feElement = event.target.closest(".fe, .cross-fe-vertical");
        if (!feElement) return;

        const feName = feElement.textContent.trim();

        if (requirementsMap.hasOwnProperty(feName)) {
            openPanel(feName);
        }
    });

    /* =========================================================
       CLOSE BUTTON HANDLER
    ========================================================== */
    document
        .querySelector(".close-btn")
        .addEventListener("click", closePanel);

</script>
</body>
</html>
