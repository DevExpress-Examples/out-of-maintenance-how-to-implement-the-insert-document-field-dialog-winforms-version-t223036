# How to implement the "Insert Document Field" dialog (WinForms version)


<p>This example demonstrates how to implement a custom "Insert Document Field" dialog to insert fields with corresponding formatting attributes into RichEditControl documents.<br />All fields are inserted into a current document position using the <a href="https://documentation.devexpress.com/#WPF/CustomDocument10467">SubDocument.Fields.Create</a> method. The key point here is that you need to obtain a corresponding sub-document which is related to the caret position, since the caret can be located in the main document, its header or footer.<br />To obtain a corresponding sub-document, the <a href="https://documentation.devexpress.com/#CoreLibraries/DevExpressXtraRichEditAPINativeDocumentRange_BeginUpdateDocumenttopic">DocumentPosition.BeginUpdateDocument</a> method is used.<br />Also, this example demonstrates how to insert expressions and results of the "<strong>IF" </strong>field<strong> </strong>calculation as nested document fields (there is a corresponding option near the "left expression", "right expression", "true result" and "false result" of the "<strong>IF" </strong>field attributes).<br /><br /></p>
<p>To built the solution demonstrated in this sample into an existing application, copy all modules and the "insertFieldIcon.png" image located in the <strong>InsertFieldModules </strong>folder and use a corresponding <strong>RegisterInsertFieldDialogCommand</strong> extension method to add the "Insert Field" command onto a current Ribbon control:<br /><strong>CS<br /></strong></p>


```cs
richEditControl1.RegisterInsertFieldDialogCommand(ribbonPageGroup1, null);
```


<p><strong>VB<br /></strong></p>


```vb
richEditControl1.RegisterInsertFieldDialogCommand(ribbonPageGroup1, Nothing)
```


<p><strong> </strong></p>

<br/>


