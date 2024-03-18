# Open for Extension Closed for Modification 

This means that the file should be open to addition of new function , without requiring to change the existing code . 

1. <b>Open for Extension : Extend a pre-exisitng method </b>
2. <b>Closed for Modification : Dont modify already working code </b>

```python 
class Report:
    def generate(self):
        return "Report Data"

class PDFReport(Report):
    def generate(self):
        data = super().generate()
        return f"PDF Report: {data}"

class ExcelReport(Report):
    def generate(self):
        data = super().generate()
        return f"Excel Report: {data}"
```

- The `Report` class provides a base method generate().
- `PDFReport` and `ExcelReport` extend Report without modifying it, adhering to the Open/Closed Principle.
- New types of reports can be added without changing the existing Report class or the other subclasses.

