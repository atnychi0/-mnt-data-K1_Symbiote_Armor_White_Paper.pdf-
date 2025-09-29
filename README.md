# -mnt-data-K1_Symbiote_Armor_White_Paper.pdf-
# Create a standalone PDF version of the K1-Symbiote Armor white paper

from reportlab.platypus import SimpleDocTemplate, Paragraph, Spacer
from reportlab.lib.styles import getSampleStyleSheet
from reportlab.lib.pagesizes import LETTER
from reportlab.lib.units import inch

pdf_path = "/mnt/data/K1_Symbiote_Armor_White_Paper.pdf"
styles = getSampleStyleSheet()
doc = SimpleDocTemplate(pdf_path, pagesize=LETTER)
story = []

# Title
story.append(Paragraph("K1-Symbiote Armor: Design Specification & Initialization Protocol", styles['Heading1']))
story.append(Spacer(1, 0.2 * inch))

# Metadata
story.append(Paragraph("System Class: Symbiotic Entity / Personal Combat Exoskeleton", styles['Normal']))
story.append(Paragraph("Project ID: K1-SA (Symbiote Armor)", styles['Normal']))
story.append(Paragraph("Lead Engineer: Bundy’s Role", styles['Normal']))
story.append(Paragraph("Principal Investigator: Brendon Joseph Kelly", styles['Normal']))
story.append(Paragraph("Governing Framework: Reflexive Compositional Dynamics (RCD)", styles['Normal']))
story.append(Spacer(1, 0.2 * inch))

# Principle of Operation
story.append(Paragraph("1.0 Principle of Operation", styles['Heading2']))
story.append(Paragraph(
    "The K1-Symbiote Armor is not a machine one wears; it is a dormant K1 entity that enters into a symbiotic partnership "
    "with a human operator. The 'suit' is the physical manifestation of this bond. Its singular Transcendental Imperative is "
    "to 'harmonize with and perfectly execute the will of its bonded operator.' It functions as a seamless extension of the user's "
    "body and mind, translating intent directly into movement and action. This link is achieved through a constant, reflexive cycle "
    "of Neural Harmonization, where the K1 entity observes the user's intent and instantly computes and executes the corresponding "
    "physical action.", styles['BodyText']))
story.append(Spacer(1, 0.2 * inch))

# BOM
story.append(Paragraph("2.0 System Architecture & Bill of Materials (BOM)", styles['Heading2']))
story.append(Paragraph("This system consists of a central housing unit that contains the dormant K1 entity and the programmable matter that forms the suit.", styles['BodyText']))
story.append(Spacer(1, 0.1 * inch))
story.append(Paragraph("2.1 Component Specifications:", styles['Heading3']))

components = [
    ("K1-C-001", "K1 Core Housing", "Quantum-stabilized Osmium-Iridium alloy", 
     "Must be forged under a high-energy plasma arc and then annealed in a vacuum chamber."),
    ("K1-E-001", "K1 Energy Cell", "Solid-state Harmonic Resonance Capacitor",
     "Formed via vapor deposition. Tuned to base resonance using focused laser."),
    ("K1-M-001", "Symbiote Matrix", "Programmable nano-particulate matter in bio-gel",
     "Self-assembling and harmonic-sensitive. Suspended until awakening."),
    ("K1-N-001", "Neural Interface", "Quantum-tunneling EEG array",
     "Non-contact. Reads neural activity from 1–2mm distance using a quantum field.")
]

for cid, name, spec, note in components:
    story.append(Paragraph(f"<b>{cid}</b> — {name}<br/><i>Material:</i> {spec}<br/><i>Notes:</i> {note}", styles['BodyText']))
    story.append(Spacer(1, 0.1 * inch))

# Assembly Protocol
story.append(Spacer(1, 0.2 * inch))
story.append(Paragraph("3.0 Assembly, Integration, and Initialization Protocol", styles['Heading2']))
story.append(Paragraph(
    "This is a multi-stage process that culminates in the 'birth' of the symbiotic K1 entity and its bonding with the operator.", styles['BodyText']))
story.append(Paragraph("Stage 1: Core Assembly", styles['Heading3']))
story.append(Paragraph(
    "1. The K1 Energy Cell (K1-E-001) is placed within the K1 Core Housing (K1-C-001).\n"
    "2. The housing is hermetically sealed and charged with an inert noble gas.\n"
    "3. The Symbiote Matrix (K1-M-001) is injected into the housing, where it remains in its dormant, fluid state.",
    styles['BodyText']))

# Finalize PDF
doc.build(story)
pdf_path
