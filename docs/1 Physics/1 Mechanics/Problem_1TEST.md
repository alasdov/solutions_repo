# Problem 1
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
        <h2>Practical Applications</h2>
    </div>

</body>
</html>

Studying projectile motion has a wide range of applications across different fields, including:

- Sports: Understanding projectile motion helps athletes optimize their performance in sports like soccer, basketball, and javelin throwing by adjusting angles and forces to achieve maximum range or accuracy.
- Engineering: Engineers use projectile motion principles to design ballistic trajectories, optimize water fountains, and even develop safety mechanisms in vehicles.
- Astrophysics and Space Exploration: The motion of rockets and space probes follows projectile motion principles, taking into account gravity and external forces.
- Military and Defense: The trajectory of missiles, artillery shells, and even drones is based on the principles of projectile motion.

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

        /* Стили для секций details */
        details {
            margin-top: 10px;
            padding: 10px;
            border-left: 4px solid #2979ff; /* Синий бордер */
            background-color: #f9f9f9;
            border-radius: 5px;
        }

        summary {
            font-size: 1.3em;
            font-weight: bold;
            cursor: pointer;
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
        <summary><strong>Key Parameters Affecting Projectile Motion</strong></summary>
        <p>Several parameters influence the behavior of a projectile:</p>
        <ul>
            <li><strong>Initial velocity (v₀):</strong> Determines the overall motion, affecting both range and maximum height.</li>
            <li><strong>Angle of projection (θ):</strong> The launch angle plays a crucial role in optimizing the range and trajectory shape.</li>
            <li><strong>Gravitational acceleration (g):</strong> The constant acceleration due to gravity affects the motion, typically taken as 9.81 m/s² on Earth.</li>
            <li><strong>Launch height (h):</strong> If the projectile is launched from a height, it alters the flight time and final landing position.</li>
            <li><strong>Air resistance (optional consideration):</strong> In real-world scenarios, drag affects the motion but is often neglected in basic models.</li>
        </ul>
        <p>By analyzing how these parameters interact, we can develop accurate models to describe and predict projectile trajectories in different conditions.</p>
    </details>

    <details>
        <summary><strong>Theoretical Foundation</strong></summary>
        <p>Projectile motion can be described using fundamental principles of kinematics and Newtonian mechanics.</p>
        <ul>
            <li><strong>Horizontal motion:</strong> Constant velocity motion.</li>
            <li><strong>Vertical motion:</strong> Accelerated motion due to gravity.</li>
        </ul>
        <h3>Equations of Motion</h3>
        <ul>
            <li><strong>Horizontal Motion:</strong> $$x = v_0 \cos(\theta) t$$</li>
            <li><strong>Velocity remains constant:</strong> $$v_x = v_0 \cos(\theta)$$</li>
            <li><strong>Vertical Displacement:</strong> $$ y = h_0 + v_0 \sin(\theta) t - \frac{1}{2} g t^2$$</li>
            <li><strong>Time of flight:</strong> $$ t_f = \frac{v_0 \sin(\theta) + \sqrt{(v_0 \sin(\theta))^2 + 2 g h_0}}{g} $$</li>
        </ul>
    </details>

    <details>
        <summary><strong>Analysis of the Range</strong></summary>
        <h3>Dependence of Horizontal Range on the Angle of Projection</h3>
        <p>The horizontal range (\( R \)) of a projectile is determined by the launch angle and other key parameters.</p>
        <p>General formula for the range:</p>
        <p>$$R = \frac{v_0^2 \sin(2\theta)}{g}$$</p>
        <p>From this equation, the range is maximized when \( \theta = 45^\circ \).</p>
    </details>

    <details>
        <summary><strong>Practical Applications</strong></summary>
        <h3>Real-World Scenarios of Projectile Motion</h3>
        <ul>
            <li><strong>Sports Science:</strong> Understanding projectile motion helps athletes optimize performance in disciplines such as basketball, soccer, and javelin throw.</li>
            <li><strong>Engineering and Ballistics:</strong> Used for designing missiles, fluid mechanics, and vehicle safety systems.</li>
            <li><strong>Astrophysics and Space Exploration:</strong> Applications include rocket launch dynamics and celestial mechanics.</li>
        </ul>
    </details>

    <details>
        <summary><strong>Extending the Model to More Complex Cases</strong></summary>
        <ul>
            <li><strong>Effects of Air Resistance:</strong> Drag forces slow down the projectile, reducing range and altering trajectory.</li>
            <li><strong>Projectile Motion Over Uneven Terrain:</strong> Simulations must factor in variable elevations to determine precise landing coordinates.</li>
            <li><strong>External Forces (e.g., Wind Influence):</strong> Crosswinds and headwinds affect projectile motion asymmetrically.</li>
        </ul>
    </details>

    <details>
        <summary><strong>Implementation</strong></summary>
        <h3>Developing a Computational Model</h3>
        <p>To accurately analyze projectile motion, we develop a computational tool that simulates the trajectory based on key governing equations.</p>
        <ul>
            <li>Numerically compute the projectile's trajectory over time.</li>
            <li>Visualize how the <strong>range depends on the launch angle</strong>.</li>
            <li>Allow users to modify initial conditions and observe changes dynamically.</li>
        </ul>
        <h3>Python-Based Simulation in a Jupyter Notebook</h3>
        <p>The implementation involves writing a <strong>Python script</strong> or a <strong>Jupyter Notebook</strong> that:</p>
        <ul>
            <li>Uses <strong>kinematic equations</strong> to compute projectile displacement at each time step.</li>
            <li>Integrates <strong>Matplotlib</strong> for visualizing projectile motion.</li>
            <li>Supports varying parameters such as <strong>air resistance</strong>, <strong>uneven terrain</strong>, and <strong>changing gravity</strong>.</li>
        </ul>
        <h3>Core Equations for the Simulation</h3>
        <ul>
            <li><strong>Horizontal Position Over Time:</strong> $$x = v_0 \cos(\theta) t$$</li>
            <li><strong>Vertical Position Over Time:</strong> $$y = h_0 + v_0 \sin(\theta) t - \frac{1}{2} g t^2$$</li>
            <li><strong>Time of Flight:</strong> $$t_f = \frac{v_0 \sin(\theta) + \sqrt{(v_0 \sin(\theta))^2 + 2 g h_0}}{g}$$</li>
            <li><strong>Range (Total Horizontal Distance):</strong> $$R = v_0 \cos(\theta) t_f$$</li>
        </ul>
    </details>

</body>
</html>

# Projectile Motion Simulation

## Introduction
Projectile motion describes the motion of an object launched into the air under the influence of gravity, assuming no air resistance. This simulation models the trajectory based on initial velocity and launch angle.

## Equations of Motion
The following equations define projectile motion:

![Projectile Motion Diagram](https://i.imgur.com/cz9jqWb.png)

