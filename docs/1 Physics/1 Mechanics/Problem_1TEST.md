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
    <title>Key Parameters Section</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        /* Стиль секции */
        details {
            margin-top: 10px;
            border-left: 4px solid #2979ff;
            background-color: #f8f9fa;
            border-radius: 5px;
            padding: 12px 15px;
            box-shadow: none;
            transition: all 0.3s ease-in-out;
        }

        /* Заголовок */
        summary {
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            background-color: #f8f9fa;
            border-radius: 5px;
            transition: background-color 0.3s ease;
            padding: 12px 15px;
            border-left: none;
            margin: -12px -15px 0 -15px;
        }

        summary:hover {
            background-color: #e0e0e0;
        }

        /* Внутренний контент */
        details div {
            padding: 10px 0;
        }

        details ul {
            padding-left: 25px;
        }

        details li {
            margin-bottom: 8px;
        }

    </style>
</head>
<body>

    <!-- Key Parameters Affecting Projectile Motion -->
    <details open>
        <summary>Key Parameters Affecting Projectile Motion</summary>
        <div>
            <p>Several parameters influence the behavior of a projectile:</p>
            <ul>
                <li><strong>Initial velocity (v₀):</strong> Determines the overall motion, affecting both range and maximum height.</li>
                <li><strong>Angle of projection (θ):</strong> The launch angle plays a crucial role in optimizing the range and trajectory shape.</li>
                <li><strong>Gravitational acceleration (g):</strong> The constant acceleration due to gravity affects the motion, typically taken as 9.81 m/s² on Earth.</li>
                <li><strong>Launch height (h):</strong> If the projectile is launched from a height, it alters the flight time and final landing position.</li>
                <li><strong>Air resistance (optional consideration):</strong> In real-world scenarios, drag affects the motion but is often neglected in basic models.</li>
            </ul>
            <p>By analyzing how these parameters interact, we can develop accurate models to describe and predict projectile trajectories in different conditions.</p>
        </div>
    </details>

</body>
</html>

