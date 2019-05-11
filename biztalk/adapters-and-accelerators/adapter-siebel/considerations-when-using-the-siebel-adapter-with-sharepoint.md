---
title: SharePoint で Siebel アダプターの使用時の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea7da079-3250-4ecc-bf01-6b5495c7f380
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee3328ea53a68688441c25c254a73e45cb94f083
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371774"
---
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a>SharePoint で Siebel アダプターの使用時の考慮事項
このトピックでには使用中に発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。 問題は、2 つのカテゴリに分類されます。  
  
-   一般的な問題  
  
-   カスタム Web パーツに関連する問題  
  
## <a name="general-issues"></a>一般的な問題  
 このセクションには、解像度を持たないか、アプリケーション定義ファイルの解像度を変更する必要がありますいずれかの問題が含まれています。  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a>問題 1:WCF サービスによって返される単純型のデータは表示されません。  
 **説明**:Microsoft Office SharePoint Server には、データセットまたはコレクション型のみにする WCF サービスによって返されるデータが必要です。 単純型の WCF サービスによって返されるデータは、Microsoft Office SharePoint Server では、データは表示されません。  
  
 **解像度**:解決策はありません。 Microsoft Office SharePoint Server に関する既知の問題になります。  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a>問題 2:WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。  
 **説明**:WCF サービスによって返されるデータが NULL 値の場合、Microsoft Office SharePoint Server には、エラー メッセージが表示されます。 たとえばのビジネス データ一覧 Web パーツを使用している、 **Finder**メソッド、インスタンス化し、検索式に基づく Siebel システムで顧客を検索します。 指定した検索式は、NULL 値を取得します。 この場合は、Microsoft Office SharePoint Server、エラー メッセージが表示されます。  
  
 **解像度**:解決策はありません。 Microsoft Office SharePoint Server に関する既知の問題になります。  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a>問題 3:WCF サービスによって返される単純型の配列は表示されません。  
 **説明**:WCF サービスによって返されるデータが単純型の配列の場合は、Microsoft Office SharePoint Server では、データが表示されません。 さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます。「バックエンド システムのアダプターから構造体 (MethodInstance、パラメーターまたは TypeDescriptor) に対応するメタデータと互換性がありません。」  
  
 **解像度**:解決策はありません。 Microsoft Office SharePoint Server およびビジネス データ カタログ定義エディターでの既知の制限事項になります。  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a>問題 4:300 を超えるフィールドを持つ複合型パラメーターを含むアプリケーション定義ファイルをインポートすることはできません。  
 **説明**:Microsoft Office SharePoint Server は、WCF サービスによって返された複合型パラメーターの 300 を超えるフィールドがあり、これを行うにしようとするとエラー メッセージが表示されるアプリケーション定義ファイルをインポートできません。 これは、複合型のパラメーターの 300 を超えるフィールドを表示することができない、Microsoft Office SharePoint Server の制限のため。  
  
 **解像度**:ビジネス データ カタログ定義エディターを使用すると、300 未満の複合型のパラメーターのフィールドの数を制限できます。 お客様の要件に応じて、ビジネス データ カタログ定義エディターで Microsoft Office SharePoint Server に表示される必要としない複合型のパラメーターのフィールドを削除できます。  またはも、すべてのフィールドと共に、アプリケーション定義ファイル キーをビジネス データ カタログ定義エディターからエクスポートし、メモ帳などないフィールドを削除する XML 作成アプリケーションでのアプリケーション定義ファイルを変更し、300 にフィールドの数を制限するために必要です。  
  
##  <a name="Custom_Web_Part"></a> カスタム Web パーツに関連する問題  
 このセクションには、問題解決するため、カスタム Web パーツの使用を必要とするにはが含まれています。 カスタム Web パーツを使用して、操作中に思いつくの問題を解決する方法については詳細な[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]および Microsoft Office SharePoint Server を参照してください[Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a>問題 1:列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます。  
 **説明**:ビジネス データ一覧または Microsoft Office SharePoint Server では、ビジネス データ項目 Web パーツには、列挙型 (列挙子と呼ばれる名前付き定数のセットで構成される異なる型) のデータが含まれている、列挙子のインデックスはでは、その値の代わりに表示されます。Microsoft Office SharePoint Server。 これは、ため、ビジネス データ一覧とビジネス データ項目の Web パーツを正しく印刷しない SharePoint ポータルに列挙型のデータの値です。  
  
 **解像度**:インデックスではなく、列挙子の値を出力するのにには、カスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。 たとえば、Microsoft Office SharePoint Server に列挙型のデータの正しい値を印刷するのに Web パーツで次のコード サンプルを使用できます。  
  
```  
namespace CustomWebpart  
{  
    public class CustomWebPart : WebPart  
    {  
        private string displayText = "Hello World!";  
  
        [WebBrowsable(true), Personalizable(true)]  
        public string DisplayText  
        {  
            get { return displayText; }  
            set { displayText = value; }  
        }  
        protected override void Render(System.Web.UI.HtmlTextWriter writer)  
        {  
            string SearchExpr = "[Address Name] LIKE \"*\"";  
            object ElementType = null;  
  
/***Step 1: Get the required entity and method.***/  
  
            LobSystem newSystem = ApplicationRegistry.GetLobSystems()["WebServiceLobSystem"]; // Name specified in application definition file  
            LobSystemInstance newSystemInstance = newSystem.GetLobSystemInstances()["Siebel_Instance"]; // Name specified in application definition file  
            Entity CategoryEntity = newSystem.GetEntities()["Siebel_Method_Name"]; // Name specified in application definition file  
            Method newMethod = CategoryEntity.GetMethods()["Query"]; // Name specified in application definition file  
            MethodInstance methodInstance = newMethod.GetMethodInstances()["MethodInstance0"]; // Name specified in application definition file  
  
/***Step 2: Get the list of input parameters.***/  
            Object[] args = methodInstance.GetMethod().CreateDefaultParameterInstances(methodInstance); // Get default value of the input parameter  
            Object[] ArgsInput = new Object[args.Length];  
  
/***Step 3: Assign them required values.***/  
  
           //Assigning values to a complex type parameter. Index of this parameter is 3rd in args array.   
           /*** Complex Type Parameter is defined as follows:  
           <Parameter Direction="In" Name="BusinessAddressQueryInputRecord">  
           <TypeDescriptor TypeName="BDC.BusinessAddressQueryInputRecord,WebServiceLobSystem" Name="BusinessAddressQueryInputRecord">  
              <TypeDescriptors>  
                 <TypeDescriptor TypeName="System.String, ...." Name="SearchExpr"></TypeDescriptor>  
                 <TypeDescriptor TypeName="System.String, ...." Name="SortSpec"></TypeDescriptor>  
                 <TypeDescriptor TypeName="System.String[], ...." IsCollection="true" Name="QueryFields"></TypeDescriptor>  
              </TypeDescriptors>  
           </TypeDescriptor>  
           </Parameter>  
            * We are assigning value to Parameter SearchExpr. ***/  
  
            Assembly asm = Assembly.GetAssembly(args[2].GetType());  
            Type t = asm.GetType(args[2].GetType().ToString()); // Get type of the parameter  
  
            FieldInfo[] FI = t.GetFields();  
            ElementType = Activator.CreateInstance(t);  
            ElementType.GetType().GetFields()[0].SetValue(ElementType, (Object)SearchExpr);  
  
            ArgsInput[2] = ElementType; // ArgsInput is fed as input while executing Method Instance.  
  
/***Step 4: Execute the particular method instance using the required value.***/              
  
            IEntityInstanceEnumerator prodEntityInstanceEnumerator = (IEntityInstanceEnumerator)CategoryEntity.Execute(methodInstance, newSystemInstance, ref ArgsInput); //Method instance of type Finder is being used here.  
  
/***Step 5: Display the output on the custom Web Part in Microsoft Office SharePoint Server.***/  
  
            writer.Write("<table>");  
            while (prodEntityInstanceEnumerator.MoveNext())  
            {  
                IEntityInstance IE = prodEntityInstanceEnumerator.Current;  
  
                writer.Write("<tr>");  
                foreach (Field f in CategoryEntity.GetFinderView().Fields)  
                {  
  
                    writer.Write("<td>");  
                    writer.Write(IE[f]);  
                    writer.Write("</td>");  
                }  
                writer.Write("</tr>");  
            }  
            writer.Write("</table>");  
  
        }  
    }  
}  
  
```  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a>問題 2:配列の要素に値を指定することはできません。  
 **説明**:WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列要素の値を指定できません。 できませんまたは使用すること、ビジネス データ一覧ビジネス データ項目の Web パーツでは、Microsoft Office SharePoint Server の WCF サービスに入力パラメーター (配列の要素) の値を指定することがわかります。 これは、配列は、アプリケーション定義ファイルで定義されている方法が原因です。  
  
 **解像度**:配列の要素に値を割り当てるには、カスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。 たとえば、手順 3 で次のコード サンプルを使用することができます"問題 1。列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"配列の要素に値を割り当てます。  
  
```  
/***Assign required values to parameters of type array.***/   
/***Assumption is that the ith parameter of Method is of type Array and all the simple type elements in the array are of type string***/  
  
            Type t = asm.GetType(args[i].GetType().ToString()); // Get type of the parameter  
            Type TElement = t.GetElementType(); // Getting type of element of array  
            int index = 5; //Size of Array  
            Array ElementArray = Array.CreateInstance(TElement, index); //Creating an array of length: index  
  
            for (int ind = 0; ind < index; ind++)  
            {  
                //Creating an instance of an element of array  
                object ElementType = Activator.CreateInstance(TElement);  
                FieldInfo[] FI = ElementType.GetType().GetFields();  
                for (int f = 0; f \< FI.Length; f++)  
                {  
                    ElementType.GetType().GetFields()[f].SetValue(ElementType, (Object)"ElementValue");  
                }  
                ElementArray.SetValue(ElementType, ind);  
            }  
  
            ArgsInput[i] = (object)ElementArray; // As shown in sample, ArgsInput is fed as input while executing Method Instance  
  
```  
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a>問題 3:複合型のパラメーターに NULL 値を指定すると制限  
 **説明**:Microsoft Office SharePoint Server では、Web パーツから複合型のパラメーターの値を指定しない場合は NULL する必要があります複合型のパラメーターの値としてに渡す WCF サービス。 ただし、複合型のパラメーターの NULL 以外の値が渡され、(単純型) の場合は、その子要素の NULL が渡されます。 これにより、適切なメッセージ スキーマと、WCF サービスに渡されるメッセージ スキーマが一致しません。 結果として、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]エラー メッセージを表示することがあります。  
  
> [!NOTE]
>  Microsoft Office SharePoint Server での Web パーツから値が渡されないときに、複合型のパラメーターの既定値を確認するで説明されているコード サンプルでは、手順 2 を使用して"問題 1。列挙子のインデックスが表示されます、列挙型のデータ型の値の代わりにします。"  
  
 **解像度**:Microsoft Office SharePoint Server での Web パーツから値が指定されていない場合、複合型のパラメーターに NULL 値を割り当てるには、カスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。  
  
###  <a name="Issue1"></a> 問題 4:複数の値に基づいて、1 つのレコードを表示する Microsoft Office SharePoint Server での制限事項  
 **説明**:Siebel システムから複数の値 (入力パラメーター) に基づく Microsoft Office SharePoint Server で 1 つのレコードを表示する場合は、次の 3 つの Web パーツ (ビジネス データ一覧、ビジネス データ項目、およびビジネス データ関連一覧) のいずれかを指定を使用できません。[手順 3。Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)で[チュートリアル 1。SharePoint サイト上の Siebel システムからのデータを表示する](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)します。  
  
 **解像度**:これを行うには、カスタム Web パーツを使用する必要があります。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。 たとえば、手順 3. で"問題 1。列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"と、1 つのビジネス コンポーネントのパラメーターへの入力を提供することではなく 1 つ以上のパラメーターの値を指定するコードを変更できます。  
  
## <a name="see-also"></a>参照  
 [SharePoint での Siebel アダプターの使用](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)