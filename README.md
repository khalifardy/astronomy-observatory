# Astronomy Observatory Control System

Sistem kontrol dan otomasi untuk observatorium astronomi pribadi. Mengintegrasikan kontrol hardware, scheduling pengamatan, dan monitoring lingkungan.

## Fitur Utama

### Hardware Control
- Kontrol teleskop dan mounting
- Manajemen kamera
- Fokusing otomatis
- Sensor monitoring

### Automation
- Scheduling pengamatan
- Weather monitoring
- Emergency shutdown
- Remote access

### Data Management
- Logging observasi
- Kalibrasi data
- Weather records
- System telemetry

## Struktur Repository

```
astronomy-observatory/
├── config/           # Konfigurasi hardware dan sistem
├── src/             # Source code
│   ├── hardware/    # Kontrol hardware
│   ├── control/     # Sistem kontrol
│   └── automation/  # Otomasi dan scheduling
├── data/            # Data observasi dan kalibrasi
└── tests/           # Unit tests
```

## Hardware Requirements

### Teleskop
- Mounting GoTo
- Auto-focuser
- Filter wheel
- Guiding system

### Kamera
- CCD/CMOS camera
- Filter set
- Guiding camera

### Sensors
- Weather station
- Cloud sensor
- Rain sensor
- Light sensor

## Setup Development Environment

1. Clone repository:
```bash
git clone https://github.com/yourusername/astronomy-observatory.git
cd astronomy-observatory
```

2. Create virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# atau
venv\Scripts\activate     # Windows
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Setup konfigurasi:
```bash
cp config/telescope_config.yaml.example config/telescope_config.yaml
cp config/camera_config.yaml.example config/camera_config.yaml
cp config/environment_config.yaml.example config/environment_config.yaml
```

## Penggunaan

### Basic Control
```python
from src.hardware.telescope import Telescope
from src.control.mount_control import Mount

# Initialize hardware
telescope = Telescope(config_file='config/telescope_config.yaml')
mount = Mount(config_file='config/mount_config.yaml')

# Basic operations
telescope.connect()
mount.goto_target(ra="20:41:25.9", dec="+45:16:49.3")
```

### Automation
```python
from src.automation.scheduling import Scheduler
from src.automation.monitoring import WeatherMonitor

# Setup automation
scheduler = Scheduler()
weather = WeatherMonitor()

# Add observation task
scheduler.add_task(target="M31", exposure=300, filter="L")
```

## Configuration

### Telescope Config
```yaml
telescope:
  model: "Celestron EdgeHD 11"
  focal_length: 2800
  aperture: 279.4
  connection:
    type: "ascom"
    port: "COM3"
```

### Camera Config
```yaml
camera:
  model: "ZWO ASI1600MM Pro"
  pixel_size: 3.8
  resolution: [4656, 3520]
  cooling: true
```

## Safety Features

### Weather Protection
- Automatic dome closing
- Rain detection
- Cloud monitoring
- Wind speed limits

### System Protection
- Emergency shutdown
- Power monitoring
- Error handling
- Backup systems

## Monitoring

### Environment
- Temperature
- Humidity
- Wind speed
- Cloud cover
- Rain detection

### System Status
- Hardware status
- Connection status
- Error logs
- Performance metrics

## Development Guidelines

### Code Style
- PEP 8 compliance
- Type hints
- Error handling
- Logging

### Testing
- Hardware simulation
- Unit testing
- Integration testing
- Safety testing

## Contributing

1. Fork repository
2. Create feature branch
3. Implement changes
4. Test thoroughly
5. Submit pull request

## Dependencies

### Required
- numpy
- astropy
- PyIndi
- alpaca-discovery
- requests

### Optional
- tensorflow (auto-focusing)
- opencv-python (image analysis)
- matplotlib (visualization)

## Project Status
- Hardware Control: Development
- Automation: Planning
- Monitoring: Active

## Roadmap
- [ ] Basic hardware control
- [ ] Weather monitoring
- [ ] Scheduling system
- [ ] Remote access
- [ ] Full automation

## Troubleshooting

### Common Issues
- Connection problems
- Hardware errors
- Configuration issues
- Automation failures

### Debug Tools
- System logs
- Status monitoring
- Diagnostic tools
- Test suites

## Contact
- Email: [your.email@domain.com]
- GitHub: [@yourusername]

## License
MIT License - see [LICENSE](LICENSE)

## Safety Warning
⚠️ This system controls expensive hardware. Always test thoroughly and implement proper safety measures.

## Notes
- Development active
- Safety first
- Regular testing required
- Documentation WIP
