---
layout: course
title: Control System Design
description: Design of low-order compensators (PID variants) using polynomial equations and frequency response approaches, dominant pole placement, constraints in SISO control, pole-zero cancellation, model matching, internal model control (IMC), time-delay systems, decoupling, RGA, and TITO pole assignment.
instructor: Assoc. Prof. İlker Üstoğlu
year: 2026
term: Spring
location: ITU Faculty of Electrical and Electronics Engineering
time: TBA
course_id: KON314E
schedule:
  - week: 1
    date: Week 1
    topic: Kontrol Sistem Tasarımına Giriş ve Ön Test
    description: Introduction to control system design fundamentals, performance criteria, and diagnostic pre-test.
    materials:
      - name: Syllabus
        url: /assets/pdf/example_pdf.pdf
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 2
    date: Week 2
    topic: Tasarım Yöntemleri ve Laboratuvar Ortamı Tanıtımı
    description: Design specifications, high-gain control, on-off control, effects of feedback, and introduction to software tools.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 3
    date: Week 3
    topic: K-Sentezi, Faz İlerlemeli/Gerilemeli Kompanzatörler (Lead/Lag)
    description: Gain synthesis (K-synthesis), phase-lag (PI), phase-lead (PD), and lead-lag controller design.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Problem Set 1
        url: /assets/pdf/example_pdf.pdf

  - week: 4
    date: Week 4
    topic: PID Kontrolör Tasarımı ve Katsayı Ayarlama Yöntemleri
    description: Classical PID synthesis, tuning rules, and transient response shaping.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: MATLAB Lab 1
        url: https://github.com/

  - week: 5
    date: Week 5
    topic: Baskın Kutup Atama ile Kontrolör Tasarımı
    description: Dominant pole placement methods and closed-loop specification mapping.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Assignment 1
        url: /assets/pdf/example_pdf.pdf

  - week: 6
    date: Week 6
    topic: Kutup-Sıfır Götürmesi, Çentik (Notch) Filtreler ve Model Eşleme
    description: Pole-zero cancellation techniques, notch filter design, and exact model matching.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 7
    date: Week 7
    topic: Geri Beslemenin Getirdiği Temel Kısıtlamalar
    description: Fundamental algebraic and analytic limitations in feedback control (Bode integrals, non-minimum phase zeros).
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Assignment 2
        url: /assets/pdf/example_pdf.pdf

  - week: 8
    date: Week 8
    topic: İki Serbestlik Dereceli Kontrol (2-DOF) ve Yıl İçi Sınavı
    description: Two-degree-of-freedom structures, setpoint weighting, PI-PD / PV controllers, and Midterm Examination.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 9
    date: Week 9
    topic: Frekans Tanım Bölgesinde K-Sentezi ve Faz Gerilemeli Kontrol
    description: Frequency-domain compensator design, loop shaping, and phase-lag network realization.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 10
    date: Week 10
    topic: Frekans Tanım Bölgesinde Faz İlerlemeli Kontrolör Tasarımı
    description: Phase-lead compensator synthesis in the frequency domain for phase/gain margin enhancement.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Assignment 3
        url: /assets/pdf/example_pdf.pdf

  - week: 11
    date: Week 11
    topic: İç Model Kontrol (IMC) ve Bozucu/Gürültü Bastırma
    description: Internal Model Control (IMC) principle, tracking robustness, and disturbance rejection.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: MATLAB Lab 2
        url: https://github.com/

  - week: 12
    date: Week 12
    topic: Zaman Gecikmeli Sistemlerin Kontrolü ve Smith Öngörücüsü
    description: Time-delay dynamics, Padé approximation, Smith Predictor, and frequency-domain delay compensation.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 13
    date: Week 13
    topic: Çok Girişli Çok Çıkışlı (MIMO/TITO) Sistemler ve RGA
    description: Analysis of Two-Input Two-Output (TITO) systems, cross-coupling, and Relative Gain Array (RGA).
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf

  - week: 14
    date: Week 14
    topic: TITO Sistemlerin Tasarımı - Dekuplaj ve Doğrudan Kutup Atama
    description: Decoupling networks, multivariable compensator design, and direct pole assignment.
    materials:
      - name: Lecture Notes
        url: /assets/pdf/example_pdf.pdf
      - name: Assignment 4
        url: /assets/pdf/example_pdf.pdf
---

## Course Overview

This course provides a comprehensive treatment of classical and modern loop-shaping compensator design for single-input single-output (SISO) and multivariable (TITO) systems:

- **Compensator Synthesis:** Root locus and frequency-domain synthesis of phase-lead, phase-lag, lead-lag, and PID variants.
- **Advanced SISO Techniques:** Dominant pole placement, exact model matching, notch filters, and Internal Model Control (IMC).
- **Fundamental Limitations:** Algebraic and dynamic trade-offs, sensor noise, actuator saturation, and sensitivity integrals.
- **Time-Delay & Multivariable Systems:** Padé approximations, Smith predictors, Relative Gain Array (RGA) interaction analysis, and dynamic decoupling controllers.
- **Hands-On Engineering:** Model-based validation and simulation in MATLAB & Mathematica environments.

## Prerequisites

- **Course Prerequisites:** `KON 313` (Min. DD) or `KON 313E` (Min. DD)
- **Required Background:** Linear control systems theory, Laplace transforms, Bode/Nyquist plots, and basic matrix algebra.

## Course Information

- **Code:** KON314E / KON314
- **Department:** Control and Automation Engineering
- **Language:** Turkish / English
- **Credits:** 3 Local Credits / 6 ECTS (2h Theoretical + 2h Laboratory)

## Textbooks & References

- *Feedback Control of Dynamic Systems* by Gene F. Franklin, J. David Powell, Abbas Emami-Naeini
- *Modern Control Systems* by Richard C. Dorf, Robert H. Bishop
- *Control System Design* by Graham C. Goodwin, Stefan F. Graebe, Mario E. Salgado

## Grading

- Midterm Exam(s): 30%
- Laboratory & MATLAB Homeworks: 30%
- Final Examination: 40%
