# Aquabotia - Software Stack (prova de conceito)

Este repositório contém uma implementação de prova de conceito do software descrito no "RELATÓRIO DESCRITIVO - Aquabotia" :contentReference[oaicite:2]{index=2}.

**Importante (segurança):** O módulo de conversão energética (reator de pirólise) é perigoso. Este repositório fornece apenas uma **interface de software** (reactor_controller) e simulações. NÃO construa reatores sem engenheiros qualificados.

## Como rodar (resumo)
1. Tenha ROS2 (Humminbird/Fox/galactic/rolling conforme sua distro) instalado.
2. Instale dependências: `pip install -r requirements.txt`
3. Monte workspace: `colcon build` na pasta `ros2_ws`
4. Fonte: `source install/setup.bash`
5. Execute nós (exemplo): `ros2 run aquabotia_core vision_node` etc.

## Componentes
- vision_node: inferência de imagens (Jetson)
- propulsion_node: interface motora (simulação)
- energy_manager: nível de bateria / política de retorno
- swarm_manager: orquestração via MQTT
- acoustic_modem_node: abstracão serial do modem acústico
- mother_drone_node: lógica de surfacing e uplink
- reactor_controller: interface segura para reator (apenas high-level)
