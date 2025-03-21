# Problem 1TEST
## Introduction and Motivation

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Styled Section Fix</title>
    <style>
        /* Исправленный стиль */
        .static-section {
            background-color: #f9f9f9; /* Светло-серый, но не слишком контрастный */
            padding: 10px 15px;
            border-left: 4px solid #5a9bff; /* Умеренно-синий бордер */
            border-radius: 4px;
            margin-bottom: 15px;
            box-shadow: none; /* Убираем тень, если она ломает макет */
            display: flex; /* Гарантия, что размер блока соответствует контенту */
            align-items: center;
        }

        .static-section h2 {
            font-size: 1.2em; /* Уменьшенный размер для соответствия другим заголовкам */
            font-weight: bold;
            color: #222; /* Чуть темнее для лучшего контраста */
            margin: 0;
        }

        /* Общие стили для остальных секций (если они сбились) */
        details {
            background-color: #f8f8f8;
            border-left: 3px solid #d1d1d1;
            padding: 8px;
            margin-bottom: 8px;
            border-radius: 4px;
        }

        summary {
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <!-- Исправленная секция -->
    <div class="static-section">
        <h2>Significance of Studying Projectile Motion</h2>
    </div>

</body>
</html>

Projectile motion is a fundamental concept in physics that describes the motion of an object launched into the air, subject only to the force of gravity. Understanding projectile motion is crucial because it provides insights into:

- The behavior of objects in free-fall and how they travel through space.
- The effects of different forces, such as gravity and air resistance, on moving bodies.
- Predicting the trajectory of objects in various real-world scenarios.

Projectile motion is not just a theoretical concept but a practical tool for engineers, scientists, and athletes who need to optimize performance in various applications.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Projectile Motion Analysis</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        details {
            margin-top: 10px;
            padding: 10px;
            border-left: 4px solid #2979ff;
            background-color: #ffffff;
            border-radius: 5px;
            transition: all 0.3s ease-in-out;
            box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        details[open] {
            background-color: #f9f9f9;
        }

        summary {
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            padding: 8px 12px;
            margin: -10px -12px;
            display: flex;
            align-items: center;
            background-color: #f1f1f1;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        summary:hover {
            background-color: #e0e0e0;
        }

        details img {
            max-width: 100%;
            height: auto;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <details>
        <summary>Key Parameters Affecting Projectile Motion</summary>
        <p>Several parameters influence the behavior of a projectile:</p>
        <ul>
            <li><strong>Initial velocity (v₀):</strong> Determines the overall motion, affecting both range and maximum height.</li>
            <li><strong>Angle of projection (θ):</strong> The launch angle plays a crucial role in optimizing the range and trajectory shape.</li>
            <li><strong>Gravitational acceleration (g):</strong> The constant acceleration due to gravity affects the motion, typically taken as 9.81 m/s² on Earth.</li>
            <li><strong>Launch height (h):</strong> If the projectile is launched from a height, it alters the flight time and final landing position.</li>
            <li><strong>Air resistance (optional consideration):</strong> In real-world scenarios, drag affects the motion but is often neglected in basic models.</li>
        </ul>
    </details>

    <details>
        <summary>Theoretical Foundation</summary>
        <h3>Equations of Motion</h3>
        <ul>
            <li><strong>Horizontal Motion:</strong> $$x = v_0 \cos(\theta) t$$</li>
            <li><strong>Velocity remains constant:</strong> $$v_x = v_0 \cos(\theta)$$</li>
            <li><strong>Vertical Displacement:</strong> $$ y = h_0 + v_0 \sin(\theta) t - \frac{1}{2} g t^2$$</li>
            <li><strong>Time of flight:</strong> $$ t_f = \frac{v_0 \sin(\theta) + \sqrt{(v_0 \sin(\theta))^2 + 2 g h_0}}{g} $$</li>
        </ul>
    </details>

    <details>
        <summary>Analysis of the Range</summary>
        <h3>Dependence of Horizontal Range on the Angle of Projection</h3>
        <p>The horizontal range (\( R \)) of a projectile is determined by the launch angle and other key parameters.</p>
        <p>$$R = \frac{v_0^2 \sin(2\theta)}{g}$$</p>
    </details>

    <details>
        <summary>Extending the Model to More Complex Cases</summary>
        <ul>
            <li><strong>Effects of Air Resistance:</strong> Drag forces slow down the projectile, reducing range and altering trajectory.</li>
            <li><strong>Projectile Motion Over Uneven Terrain:</strong> Simulations must factor in variable elevations to determine precise landing coordinates.</li>
            <li><strong>External Forces (e.g., Wind Influence):</strong> Crosswinds and headwinds affect projectile motion asymmetrically.</li>
        </ul>
    </details>

    <details>
        <summary>Implementation</summary>
        <h3>Developing a Computational Model</h3>
        <ul>
            <li>Numerically compute the projectile's trajectory over time.</li>
            <li>Visualize how the <strong>range depends on the launch angle</strong>.</li>
            <li>Allow users to modify initial conditions and observe changes dynamically.</li>
        </ul>
    </details>

    <details>
        <summary>Generating Graphical Representations</summary>
        <p>To explore the relationship between <strong>range and launch angle</strong>, we generate <strong>graphs</strong> using <strong>Matplotlib</strong>:</p>
        <ul>
            <li><strong>Plot 1:</strong> The <strong>trajectory of the projectile</strong> for different angles.</li>
            <li><strong>Plot 2:</strong> A <strong>Range vs. Angle</strong> curve to show the optimal launch angle for maximum range.</li>
        </ul>
        <img src="path/to/graph.png" alt="Projectile Motion Trajectory">
    </details>

    <details>
        <summary>Future Extensions</summary>
        <p>This simulation can be further enhanced by:</p>
        <ul>
            <li><strong>Including air resistance:</strong> Accounting for drag force to improve real-world accuracy.</li>
            <li><strong>Simulating motion on uneven terrain:</strong> Adjusting equations to consider variable landing heights.</li>
            <li><strong>Interactive elements:</strong> Implementing sliders or input fields in a <strong>Jupyter Notebook</strong> for real-time parameter tuning.</li>
        </ul>
    </details>

</body>
</html>


 