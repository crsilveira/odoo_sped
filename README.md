# odoo_sped
Sped ICMS-IPI


Adicionado na invoice_eletronic o campo :

class InvoiceEletronic(models.Model):
    _inherit = 'invoice.eletronic'
    
    ... 
    
    emissao_doc = fields.Selection([
        ('1', u'1 - Emissão Própria'),
        ('2', u'2 - Terceiros'),
        ], u'Indicador do Emitente', readonly=True, 
        states=STATE, required=False, default='1')
        
        
 class InvoiceEletronicItem(models.Model):
    _inherit = "invoice.eletronic.item"
    
    
    num_item = fields.Integer(
        string=u"Sequêncial Item", default=1, readonly=True, states=STATE)
        
        
