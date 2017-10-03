---
title: "SharePoint で Siebel アダプターの使用時の考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea7da079-3250-4ecc-bf01-6b5495c7f380
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1df22d3eb20dc6286d5b85c3648db98518f23e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a>SharePoint で Siebel アダプターの使用時の考慮事項
このトピックの内容には使用しているときに発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。 問題は、2 つのカテゴリに分けられます。  
  
-   一般的な問題  
  
-   カスタム Web パーツに関連する問題  
  
## <a name="general-issues"></a>一般的な問題  
 このセクションには、問題解決が必要ないか、アプリケーション定義ファイルの解像度を変更する必要がありますが含まれています。  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a>問題 1: WCF サービスによって返される単純型のデータは表示されません。  
 **説明**: Microsoft Office SharePoint Server は、データセットまたはコレクションの型だけにする WCF サービスによって返されるデータを期待します。 WCF サービスによって返されるデータが単純型である場合、Microsoft Office SharePoint Server では、データが表示されません。  
  
 **解像度**: 解決策はありません。 これは、Microsoft Office SharePoint Server に関する既知の問題です。  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a>問題 2: WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。  
 **説明**: WCF サービスによって返されるデータが NULL 値の場合は、Microsoft Office SharePoint Server がエラー メッセージを表示します。 たとえば、ビジネス データ一覧 Web パーツを使用している、 **Finder**メソッドをインスタンス化、および検索式に基づく Siebel システムで顧客の検索を実行します。 指定した検索式では、NULL 値をフェッチします。 この例では、Microsoft Office SharePoint Server、エラー メッセージが表示されます。  
  
 **解像度**: 解決策はありません。 これは、Microsoft Office SharePoint Server に関する既知の問題です。  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a>問題 3: WCF サービスによって返される単純型の配列は表示されません。  
 **説明**: Microsoft Office SharePoint Server にデータが表示されない場合は、WCF サービスによって返されるデータが単純型の配列。 さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます:"システム アダプターがバックエンド返された構造体、対応するメタデータ (と互換性がありませんMethodInstance、パラメーターまたは TypeDescriptor)。"  
  
 **解像度**: 解決策はありません。 Microsoft Office SharePoint Server とビジネス データ カタログ定義エディターで、既知の制限することをお勧めします。  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a>問題 4: が 300 を超えるフィールドを持つ複合型パラメーターを含んでいるアプリケーション定義ファイルをインポートできません。  
 **説明**: Microsoft Office SharePoint Server が WCF サービスによって返される、複合型パラメーターで 300 を超えるフィールドがあり、これを行うにしようとすると、エラー メッセージを表示するアプリケーション定義ファイルをインポートできません。 これは、複合型パラメーターの 300 を超えるフィールドを表示することはできませんの Microsoft Office SharePoint Server の制限のためです。  
  
 **解像度**: エディターを使用して、ビジネス データ カタログ定義 300 未満に複合型パラメーターのフィールドの数を制限します。 必要に応じての複合型パラメーターで、ビジネス データ カタログ定義エディターするを必要としない Microsoft Office SharePoint Server に表示されるフィールドを削除できます。  代わりに、エクスポートも、アプリケーション定義ファイル ビジネス データ カタログ定義エディターからすべてのフィールドがおよび、メモ帳などされていないフィールドを削除する XML オーサリング アプリケーションで、アプリケーション定義ファイルを変更できます。300 にフィールドの数を制限するために必要です。  
  
##  <a name="Custom_Web_Part"></a>カスタム Web パーツに関連する問題  
 このセクションには、問題解決するためのカスタム Web パーツの使用を必要とするにはが含まれています。 詳細については、使用中に生じる可能性があります問題を解決するのには、カスタム Web パーツを使用して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]および Microsoft Office SharePoint Server を参照してください[Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a>問題 1: 列挙子のインデックスは、列挙型のデータ型の値の代わりに表示されます。  
 **説明**: 列挙子のインデックスは、ビジネス データ一覧または Microsoft Office SharePoint Server でビジネス データ項目 Web パーツには列挙型 (が特殊な種類の列挙子と呼ばれる名前付き定数のセットで構成される) のデータがある場合Microsoft Office SharePoint Server でその値の代わりに表示されます。 これは、ため、ビジネス データ一覧とビジネス データ項目 Web パーツを正しく印刷いない SharePoint ポータルに、列挙型のデータの値です。  
  
 **解像度**: インデックスではなく、列挙子の値を出力するカスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。 たとえば、Microsoft Office SharePoint Server に列挙型のデータの正しい値を印刷するのに Web パーツで次のコード サンプルを使用することができます。  
  
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
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a>問題 2: 配列の要素に値を指定できません。  
 **説明**: WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列の要素に値を指定することはできません。 使用することできませんビジネス データ一覧またはビジネス データ項目の Web パーツ Microsoft Office SharePoint Server でこれらの入力パラメーター (配列の要素) WCF サービスへの値を指定を意味します。 これは、配列が、アプリケーション定義ファイルで定義されているためです。  
  
 **解像度**: 配列要素に値を割り当てるカスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。 手順 3 で、次のコード サンプルを使用するなど、"問題 1: 列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"配列の要素に値を割り当てます。  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a>複合型のパラメーターに NULL 値を指定することで問題 3: 制限  
 **説明**: Microsoft Office SharePoint Server で、Web パーツからの複合型パラメーターのすべての値を指定しないと場合、NULL として渡す必要複合型のパラメーターの値、WCF サービスにします。 ただし、NULL 以外の値が、複合型パラメーターに渡され、単純型の場合は、その子要素に対して NULL が渡されました。 これにより、予期されるメッセージ スキーマと WCF サービスに渡されるメッセージ スキーマの不一致が原因です。 その結果、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]エラー メッセージを表示する場合があります。  
  
> [!NOTE]
>  Microsoft Office SharePoint Server での Web パーツから値が渡されない場合、複合型パラメーターの既定値を調べるに記載されているコード サンプルでは、手順 2 を使用して"問題 1: 列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"。  
  
 **解像度**: Microsoft Office SharePoint Server での Web パーツから値が指定されていない場合、複合型パラメーターに NULL 値を割り当てるカスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。  
  
###  <a name="Issue1"></a>問題 4: 複数の値に基づいて Microsoft Office SharePoint Server で 1 つのレコードを表示するオプションと制限  
 **説明**: Microsoft Office SharePoint server、Siebel システムから複数の値 (入力パラメーター) に基づく 1 つのレコードを表示する場合は、次の 3 つの Web パーツ (のビジネス データ一覧、ビジネス データ項目、および Business のいずれかを使用できません指定されたデータ関連一覧)[手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)で[チュートリアル 1: 提示データ Siebel システムから SharePoint サイトで](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)です。  
  
 **解像度**: これを行うカスタム Web パーツを使用する必要があります。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。 たとえば、手順 3 で"問題 1: 列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"1 つのビジネス コンポーネントのパラメーターへの入力を提供する代わりに 1 つ以上のパラメーターの値を指定するコードを変更することができます。  
  
## <a name="see-also"></a>参照  
 [SharePoint での Siebel アダプターを使用します。](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)