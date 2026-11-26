---
layout: about
title: about
permalink: /
seo_title: Moein Sarbandi | Automatic Control, Centrale Nantes
subtitle: >
  Marie Skłodowska-Curie PhD Fellow in Automatic Control ·
  <a href="https://www.ec-nantes.fr" target="_blank">Centrale Nantes</a> ·
  <a href="https://dense-dn.eu/" target="_blank">DENSE Doctoral Network</a> ·
  <a href="https://www.ls2n.fr" target="_blank">LS2N Research Laboratory</a>

profile:
  align: right
  image: prof_pic.jpg
  image_alt: Portrait of Moein Sarbandi
  image_circular: true
  more_info: >
    <p>École Centrale Nantes</p>
    <p>Nantes, France</p>
    <p>Email: <a href="mailto:moein.sarbandi@ec-nantes.fr">moein.sarbandi@ec-nantes.fr</a></p>

selected_papers: true
social: true

announcements:
  enabled: true
  scrollable: true
  limit: 5

latest_posts:
  enabled: false
  scrollable: true
  limit: 3
---

I am an MSCA doctoral researcher in Automatic Control at the [Laboratory of Digital Sciences of Nantes (LS2N)](https://www.ls2n.fr/) (CODEx group), [École Centrale Nantes](https://www.ec-nantes.fr), funded by the [DENSE Doctoral Network](https://dense-dn.eu/) under Horizon Europe. My PhD research is supervised by [Prof. Franck Plestan](https://scholar.google.fr/citations?user=fJNH7aQAAAAJ&hl=en) and [Prof. Mohamed Assaad Hamida](https://scholar.google.com/citations?user=Bx-jJ64AAAAJ&hl=en).

My research focuses on robust nonlinear control, data-driven control, and learning-enhanced control of uncertain dynamical systems, with applications to floating offshore wind turbine (FOWT) control. In particular, I study data-driven sliding-mode control, data informativity for control, super-twisting algorithms, adaptive integral sliding-mode control, and nonlinear observers, including wind-speed estimation. I use MATLAB/Simulink and OpenFAST for simulation and software-in-the-loop validation. In [Wind Energy Science](https://wes.copernicus.org/articles/11/2405/2026/), my co-authors and I validated a sliding-mode approach to wind-speed estimation in OpenFAST and in a scaled experiment.

### Research interests

- **Adaptive and robust nonlinear control:** integral sliding-mode control, super-twisting algorithms, adaptive-gain methods, and CLF-QP
- **Data-driven control:** Willems' Fundamental Lemma, robust informativity using QMI/S-lemma tools, Koopman-operator methods, and DeePC
- **Learning-based control:** online neural networks integrated with classical sliding-mode designs
- **Predictive control:** model predictive control and data-enabled predictive control
- **Nonlinear observers:** second-order sliding-mode observers for state, disturbance, wind-speed, and aerodynamic-parameter estimation
- **Applications:** renewable-energy systems, especially floating offshore wind turbines

### Research mobility and collaboration

I have undertaken DENSE research secondments on data-driven control at [BTU Cottbus–Senftenberg](https://www.b-tu.de/en/) and at the [Sustainable Power Systems Lab](https://sps-lab.org/) at Cyprus University of Technology. I also collaborate with [Prof. Antonella Ferrara’s group](https://scholar.google.com/citations?user=r5JuMskAAAAJ&hl=en) at the University of Pavia.

### Academic service

I have completed 35+ peer reviews across 12 journals and review for control conferences, as detailed under [academic activities]({{ '/activities/' | relative_url }}).

See my [publications]({{ '/publications/' | relative_url }}) and [ORCID record](https://orcid.org/0000-0002-9936-5792). I welcome research collaborations in nonlinear control, data-driven methods, wind energy, robotics, and autonomous systems.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ProfilePage",
  "@id": "https://moeinsarbandi.github.io/#profile",
  "url": "https://moeinsarbandi.github.io/",
  "name": "Moein Sarbandi, Automatic Control Researcher",
  "mainEntity": {
    "@type": "Person",
    "@id": "https://moeinsarbandi.github.io/#person",
    "name": "Moein Sarbandi",
    "url": "https://moeinsarbandi.github.io/",
    "image": "https://moeinsarbandi.github.io/assets/img/prof_pic.jpg",
    "jobTitle": "Marie Skłodowska-Curie PhD Fellow in Automatic Control",
    "description": "Researcher in data-driven control, robust nonlinear control, sliding-mode control, super-twisting algorithms and floating offshore wind turbine control.",
    "affiliation": [
      {
        "@type": "Organization",
        "name": "École Centrale Nantes",
        "url": "https://www.ec-nantes.fr/"
      },
      {
        "@type": "Organization",
        "name": "Laboratory of Digital Sciences of Nantes (LS2N)",
        "url": "https://www.ls2n.fr/"
      },
      {
        "@type": "Organization",
        "name": "DENSE Doctoral Network",
        "url": "https://dense-dn.eu/"
      }
    ],
    "alumniOf": {
      "@type": "CollegeOrUniversity",
      "name": "K. N. Toosi University of Technology"
    },
    "sameAs": [
      "https://orcid.org/0000-0002-9936-5792",
      "https://scholar.google.com/citations?user=gKYz7bcAAAAJ",
      "https://www.linkedin.com/in/moein-sarbandi-2a3310252/",
      "https://github.com/MoeinSarbandi",
      {{ site.data.socials.dblp_url | jsonify }}
    ],
    "knowsAbout": [
      "Automatic control",
      "Robust nonlinear control",
      "Data-driven control",
      "Data-driven sliding-mode control",
      "Data informativity for control",
      "Willems' Fundamental Lemma",
      "Super-twisting control",
      "Adaptive integral sliding-mode control",
      "Nonlinear observers",
      "Koopman operator methods",
      "Data-enabled predictive control (DeePC)",
      "Floating offshore wind turbine control",
      "Wind speed estimation",
      "OpenFAST"
    ]
  }
}
</script>
