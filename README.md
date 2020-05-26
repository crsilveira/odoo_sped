# odoo_sped

Modulo em desuso, substituido pelo br_sped_base (Trust-Code), 
e pelos modulos  br_sped_efd_icms_ipi, e br_sped_efd_contribuicoes



Sped ICMS-IPI

Modulo nfe_purchase_import , não é utilizado mais, o xml de entrada é importado direto no invoice_eletronic , com o modulo br_account_invoice_xml.

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
        
        
