---
title: SharePoint で Oracle Business Suite アダプターの使用に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56de6267-ec34-4bd2-abd1-3f2b69876b36
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94dd9bd4f3c80ba76edc2d84fa8757336183802
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375599"
---
# <a name="considerations-using-the-oracle-business-suite-adapter-with-sharepoint"></a>SharePoint で Oracle Business Suite アダプターの使用に関する考慮事項
このトピックでには使用中に発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。 問題は、2 つのカテゴリに分類されます。  
  
-   一般的な問題  
  
-   カスタム Web パーツに関連する問題  
  
## <a name="general-issues"></a>一般的な問題  
 このセクションには、解像度が問題が含まれていません。  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a>問題 1:WCF サービスによって返される単純型のデータは表示されません。  
 **説明**:Microsoft Office SharePoint Server には、データセットまたはコレクション型のみにする WCF サービスによって返されるデータが必要です。 単純型の WCF サービスによって返されるデータは、Microsoft Office SharePoint Server では、データは表示されません。  
  
 **解像度**:解決策はありません。 Microsoft Office SharePoint Server に関する既知の問題になります。  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a>問題 2:WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。  
 **説明**:WCF サービスによって返されるデータが NULL 値の場合、Microsoft Office SharePoint Server には、エラー メッセージが表示されます。 たとえばのビジネス データ一覧 Web パーツを使用している、 **Finder**メソッド インスタンス、および検索式に基づいて、Oracle E-business Suite での顧客を検索します。 指定した検索式は、NULL 値を取得します。 この場合は、Microsoft Office SharePoint Server、エラー メッセージが表示されます。  
  
 **解像度**:解決策はありません。 Microsoft Office SharePoint Server に関する既知の問題になります。  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a>問題 3:WCF サービスによって返される単純型の配列は表示されません。  
 **説明**:WCF サービスによって返されるデータが単純型の配列の場合は、Microsoft Office SharePoint Server では、データが表示されません。 さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます。「バックエンド システムのアダプターから構造体 (MethodInstance、パラメーターまたは TypeDescriptor) に対応するメタデータと互換性がありません。」  
  
 **解像度**:解決策はありません。 Microsoft Office SharePoint Server およびビジネス データ カタログ定義エディターでの既知の制限事項になります。  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a>問題 4:300 を超えるフィールドを持つ複合型パラメーターを含むアプリケーション定義ファイルをインポートすることはできません。  
 **説明**:Microsoft Office SharePoint Server は、WCF サービスによって返された複合型パラメーターの 300 を超えるフィールドがあり、これを行うにしようとするとエラー メッセージが表示されるアプリケーション定義ファイルをインポートできません。 これは、複合型のパラメーターの 300 を超えるフィールドを表示することができない、Microsoft Office SharePoint Server の制限のため。  
  
 **解像度**:ビジネス データ カタログ定義エディターを使用すると、300 未満の複合型のパラメーターのフィールドの数を制限できます。 お客様の要件に応じて、ビジネス データ カタログ定義エディターで Microsoft Office SharePoint Server に表示される必要としない複合型のパラメーターのフィールドを削除できます。  またはも、すべてのフィールドと共に、アプリケーション定義ファイル キーをビジネス データ カタログ定義エディターからエクスポートし、メモ帳などないフィールドを削除する XML 作成アプリケーションでのアプリケーション定義ファイルを変更し、300 にフィールドの数を制限するために必要です。  
  
##  <a name="Custom_Web_Part"></a> カスタム Web パーツに関連する問題  
 このセクションには、解決するためのカスタム Web パーツを使用する必要のある問題が含まれています。 カスタム Web パーツを使用して、操作中に思いつくの問題を解決する方法については詳細な[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]および Microsoft Office SharePoint Server を参照してください[Oracle E-business Suite でカスタム web パーツを使用する方法](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)します。  
  
###  <a name="Issue1"></a> 問題 1:複数の値に基づいて、1 つのレコードを表示する Microsoft Office SharePoint Server での制限事項  
 **説明**:Oracle E-business Suite から複数の値 (入力パラメーター) に基づく Microsoft Office SharePoint Server で 1 つのレコードを表示する場合は、次の 3 つの Web パーツ (ビジネス データ一覧、ビジネス データ項目、およびビジネス データ関連一覧) のいずれかを使用できません。手順 3 で指定します。Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成[チュートリアル。SharePoint サイト上の Oracle E-business Suite からデータを提示](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)します。  
  
 **解像度**:これを行うには、カスタム Web パーツを使用する必要があります。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Oracle E-business Suite でカスタム web パーツを使用する方法](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)します。 "手順 1。カスタム Web パーツの作成"のトピック、手順 5. で、次のコード サンプルを使用することができます。 次のコード サンプルは BankCountry と BankKey、入力パラメーターとして受け取り、Microsoft Office SharePoint Server の 1 つのレコードとして表示されます。  
  
```  
namespace CustomWebPart  
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
            string BankCountry = "US";  
            string BankKey = "134329042";  
  
/***Step 1: Get the required entity and method.***/  
  
            LobSystem newSystem = ApplicationRegistry.GetLobSystems()["BAPI_BANK_GETDETAIL"]; // Name specified in application definition file  
            LobSystemInstance newSystemInstance = newSystem.GetLobSystemInstances()["BAPI_BANK_GETDETAIL_Instance"]; // Name specified in application definition file  
            Entity CategoryEntity = newSystem.GetEntities()["Entity"]; // Name specified in application definition file  
            Method newMethod = CategoryEntity.GetMethods()["BAPI_BANK_GETDETAIL"]; // Name specified in application definition file  
            MethodInstance methodInstance = newMethod.GetMethodInstances()["MethodInstance"]; // Name specified in application definition file  
  
/***Step 2: Get the list of input parameters.***/  
  
            Object[] args = methodInstance.GetMethod().CreateDefaultParameterInstances(methodInstance); //Get the default values of the input parameters.  
            Object[] ArgsInput = new Object[args.Length];  
  
/***Step 3: Assign them required values.***/  
  
            Type t = null;  
            char[] myString = BankCountry.ToCharArray();  
            String s = new String(myString);  
            t = s.GetType();  
            ArgsInput[0] = Activator.CreateInstance(t, myString);  
  
            myString = BankKey.ToCharArray();  
            s = new String(myString);  
            t = s.GetType();  
            ArgsInput[1] = Activator.CreateInstance(t, myString);  
  
/***Step 4: Execute the particular method instance using the required value.***/  
  
            IEntityInstance IE = (IEntityInstance)CategoryEntity.Execute(methodInstance, newSystemInstance, ref ArgsInput); //Method instance of type Specific Finder is being used here.  
  
/***Step 5: Display the output on the custom Web Part in Microsoft Office SharePoint Server.***/  
  
            writer.Write("<table>");  
            writer.Write("<tr>");  
            foreach (Field f in CategoryEntity.GetFinderView().Fields)  
            {  
                writer.Write("<td>");  
                writer.Write(IE[f]);  
                writer.Write("</td>");  
            }  
            writer.Write("</tr>");  
            writer.Write("</table>");  
        }  
    }  
  
```  
  
> [!NOTE]
>  アプリケーション定義ファイルを含める必要があります、 **Specificfinder**メソッドのインスタンス。 A **Specificfinder**メソッド識別子に基づいて特定のレコードを検索します。 作成する方法については、 **Specificfinder**メソッドのインスタンスを参照してください"要件 2。詳細を取得、顧客の一覧から特定の顧客"で[手順 2。Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)で[チュートリアル。SharePoint サイト上の Oracle E-business Suite からデータを提示](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)します。  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a>問題 2:配列の要素に値を指定することはできません。  
 **説明**:WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列要素の値を指定できません。 できませんまたは使用すること、ビジネス データ一覧ビジネス データ項目の Web パーツでは、Microsoft Office SharePoint Server の WCF サービスに入力パラメーター (配列の要素) の値を指定することがわかります。 これは、配列は、アプリケーション定義ファイルで定義されている方法が原因です。  
  
 **解像度**:配列の要素に値を割り当てるには、カスタム Web パーツを使用します。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Oracle E-business Suite でカスタム web パーツを使用する方法](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)します。 たとえば、手順 3 で次のコード サンプルを使用することができます"問題 1。Microsoft Office SharePoint Server での 1 つのレコードの表示の制限事項は、複数の値に基づく"配列の要素に値を割り当てます。  
  
```  
/***Assign required values to parameters of type array.***/   
/***Assumption is that the ith parameter of Method is of type Array and all the simple type elements in the array are of string type.***/  
  
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
 **説明**:Microsoft Office SharePoint Server では、Web パーツから複合型のパラメーターの値を指定しない場合は NULL する必要があります複合型のパラメーターの値としてに渡す WCF サービス。 ただし、複合型のパラメーターの NULL 以外の値が渡され、(単純型) の場合は、その子要素の NULL が渡されます。 これにより、適切なメッセージ スキーマと、WCF サービスに渡されるメッセージ スキーマが一致しません。 結果として、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]エラー メッセージを表示することがあります。  
  
> [!NOTE]
>  Microsoft Office SharePoint Server での Web パーツから値が渡されないときに、複合型のパラメーターの既定値を確認するで説明されているコード サンプルでは、手順 2 を使用して"問題 1。Microsoft Office SharePoint Server での 1 つのレコードの表示の制限に基づく複数の値。"  
  
 **解像度**:カスタム Web パーツを使用して、複合型パラメーターに NULL 値を割り当てます。 カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Oracle E-business Suite でカスタム web パーツを使用する方法](../../adapters-and-accelerators/adapter-oracle-ebs/how-to-use-a-custom-web-part-with-oracle-e-business-suite.md)します。  
  
## <a name="see-also"></a>参照  
[SharePoint で Oracle E-business Suite アダプターを使用します。](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)