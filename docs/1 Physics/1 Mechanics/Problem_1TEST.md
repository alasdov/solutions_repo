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
    <title>Key Parameters Section</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        details {
            margin-top: 10px;
            padding: 10px;
            border-left: 4px solid #2979ff;
            background-color: #f9f9f9;
            border-radius: 5px;
            transition: all 0.3s ease-in-out;
            box-shadow: none;
        }

        details[open] {
            background-color: #f1f1f1;
        }

        summary {
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            padding: 10px;
            display: flex;
            align-items: center;
            background-color: #f1f1f1;
            border-radius: 5px;
            transition: background-color 0.3s ease;
            border-left: 4px solid #2979ff;
        }

        summary:hover {
            background-color: #e0e0e0;
        }

        details p,
        details ul {
            padding: 0 15px;
            margin-bottom: 10px;
        }

        details ul {
            padding-left: 30px;
        }

        details li {
            margin-bottom: 5px;
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
        <p>By analyzing how these parameters interact, we can develop accurate models to describe and predict projectile trajectories in different conditions.</p>
    </details>

</body>
</html>
