---
title: "SharePoint での SAP アダプターの使用時の考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d310741-b648-4028-a75f-35b843edcc8d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07aef41626c9ac2336565cdca9fa3470bf0144e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-the-sap-adapter-with-sharepoint"></a><span data-ttu-id="c9920-102">SharePoint での SAP アダプターの使用時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c9920-102">Considerations when using the SAP adapter with SharePoint</span></span>
<span data-ttu-id="c9920-103">このトピックの内容には使用しているときに発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="c9920-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="c9920-104">問題は、2 つのカテゴリに分けられます。</span><span class="sxs-lookup"><span data-stu-id="c9920-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="c9920-105">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="c9920-105">General issues</span></span>  
  
-   <span data-ttu-id="c9920-106">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="c9920-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="c9920-107">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="c9920-107">General Issues</span></span>  
 <span data-ttu-id="c9920-108">このセクションには、問題解決が必要ないか、アプリケーション定義ファイルの解像度を変更する必要がありますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9920-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="c9920-109">問題 1: WCF サービスによって返される単純型のデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c9920-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="c9920-110">**説明**: Microsoft Office SharePoint Server は、データセットまたはコレクションの型だけにする WCF サービスによって返されるデータを期待します。</span><span class="sxs-lookup"><span data-stu-id="c9920-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="c9920-111">WCF サービスによって返されるデータが単純型である場合、Microsoft Office SharePoint Server では、データが表示されません。</span><span class="sxs-lookup"><span data-stu-id="c9920-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="c9920-112">**解像度**: 解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="c9920-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="c9920-113">これは、Microsoft Office SharePoint Server に関する既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="c9920-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="c9920-114">問題 2: WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9920-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="c9920-115">**説明**: WCF サービスによって返されるデータが NULL 値の場合は、Microsoft Office SharePoint Server がエラー メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9920-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="c9920-116">たとえば、ビジネス データ一覧 Web パーツを使用している、 **Finder**メソッドをインスタンス化、および検索式に基づく SAP システムで顧客の検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9920-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the SAP system based on a search expression.</span></span> <span data-ttu-id="c9920-117">指定した検索式では、NULL 値をフェッチします。</span><span class="sxs-lookup"><span data-stu-id="c9920-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="c9920-118">この例では、Microsoft Office SharePoint Server、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9920-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="c9920-119">**解像度**: 解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="c9920-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="c9920-120">これは、Microsoft Office SharePoint Server に関する既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="c9920-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="c9920-121">問題 3: WCF サービスによって返される単純型の配列は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c9920-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="c9920-122">**説明**: Microsoft Office SharePoint Server にデータが表示されない場合は、WCF サービスによって返されるデータが単純型の配列。</span><span class="sxs-lookup"><span data-stu-id="c9920-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="c9920-123">さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます:"システム アダプターがバックエンド返された構造体、対応するメタデータ (と互換性がありませんMethodInstance、パラメーターまたは TypeDescriptor)。"</span><span class="sxs-lookup"><span data-stu-id="c9920-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="c9920-124">**解像度**: 解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="c9920-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="c9920-125">Microsoft Office SharePoint Server とビジネス データ カタログ定義エディターで、既知の制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9920-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="c9920-126">問題 4: が 300 を超えるフィールドを持つ複合型パラメーターを含んでいるアプリケーション定義ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="c9920-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="c9920-127">**説明**: Microsoft Office SharePoint Server が WCF サービスによって返される、複合型パラメーターで 300 を超えるフィールドがあり、これを行うにしようとすると、エラー メッセージを表示するアプリケーション定義ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="c9920-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="c9920-128">これは、複合型パラメーターの 300 を超えるフィールドを表示することはできませんの Microsoft Office SharePoint Server の制限のためです。</span><span class="sxs-lookup"><span data-stu-id="c9920-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="c9920-129">**解像度**: エディターを使用して、ビジネス データ カタログ定義 300 未満に複合型パラメーターのフィールドの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="c9920-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="c9920-130">必要に応じての複合型パラメーターで、ビジネス データ カタログ定義エディターするを必要としない Microsoft Office SharePoint Server に表示されるフィールドを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c9920-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="c9920-131">代わりに、エクスポートも、アプリケーション定義ファイル ビジネス データ カタログ定義エディターからすべてのフィールドがおよび、メモ帳などされていないフィールドを削除する XML オーサリング アプリケーションで、アプリケーション定義ファイルを変更できます。300 にフィールドの数を制限するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c9920-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <span data-ttu-id="c9920-132"><a name="Custom_Web_Part"></a>カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="c9920-132"><a name="Custom_Web_Part"></a> Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="c9920-133">このセクションには、問題解決するためのカスタム Web パーツの使用を必要とするにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9920-133">This section contains issues that require the use of custom Web Part for a resolution.</span></span> <span data-ttu-id="c9920-134">詳細については、使用中に生じる可能性があります問題を解決するのには、カスタム Web パーツを使用して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]および Microsoft Office SharePoint Server を参照してください[SAP アダプタでカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9920-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span>  
  
###  <span data-ttu-id="c9920-135"><a name="Issue1"></a>問題 1: 複数の値に基づいて Microsoft Office SharePoint Server で 1 つのレコードを表示するオプションと制限</span><span class="sxs-lookup"><span data-stu-id="c9920-135"><a name="Issue1"></a> Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="c9920-136">**説明**: Microsoft Office SharePoint server、SAP システムから複数の値 (入力パラメーター) に基づく 1 つのレコードを表示する場合は、次の 3 つの Web パーツ (のビジネス データ一覧、ビジネス データ項目、および Business のいずれかを使用できません指定されたデータ関連一覧)[手順 3: SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)で[チュートリアル 1: SharePoint サイト上の SAP システムからデータを表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9920-136">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from an SAP system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="c9920-137">**解像度**: これを行うカスタム Web パーツを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9920-137">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="c9920-138">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [SAP アダプタでカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9920-138">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span> <span data-ttu-id="c9920-139">"手順 1:: 作成、カスタムの Web パーツで"このトピックで、手順 5. で次のコード サンプルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c9920-139">In “Step 1: Create a Custom Web Part” of that topic, you can use the following code sample in step 5.</span></span> <span data-ttu-id="c9920-140">次のコード サンプルでは、BankCountry および BankKey、入力パラメーターとして取得され、Microsoft Office SharePoint Server で 1 つのレコードとしてに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9920-140">The following code sample takes BankCountry and BankKey as the input parameters, and then displays them as a single record in Microsoft Office SharePoint Server.</span></span>  
  
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
>  <span data-ttu-id="c9920-141">アプリケーション定義ファイルを含める必要があります、 **Specific Finder**メソッド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c9920-141">The application definition file must contain the **Specific Finder** method instance.</span></span> <span data-ttu-id="c9920-142">A **Specific Finder**メソッドは、識別子に基づく特定のレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="c9920-142">A **Specific Finder** method finds a specific record based on an identifier.</span></span> <span data-ttu-id="c9920-143">作成する方法について、 **Specific Finder**メソッド インスタンスの「要件 2:: 取得の詳細、特定顧客から、一覧のお客様向け」を参照してください[手順 2: SAP のアプリケーション定義ファイルを作成成果物](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)で[チュートリアル 1: SharePoint サイト上の SAP システムからデータを表現する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9920-143">For information about creating a **Specific Finder** method instance, see “Requirement 2: Retrieve Details for a Specific Customer from the List of Customers” in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="c9920-144">問題 2: 配列の要素に値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="c9920-144">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="c9920-145">**説明**: WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列の要素に値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c9920-145">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="c9920-146">使用することできませんビジネス データ一覧またはビジネス データ項目の Web パーツ Microsoft Office SharePoint Server でこれらの入力パラメーター (配列の要素) WCF サービスへの値を指定を意味します。</span><span class="sxs-lookup"><span data-stu-id="c9920-146">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="c9920-147">これは、配列が、アプリケーション定義ファイルで定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="c9920-147">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="c9920-148">**解像度**: 配列要素に値を割り当てるカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9920-148">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="c9920-149">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [SAP アダプタでカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9920-149">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span> <span data-ttu-id="c9920-150">手順 3 で、次のコード サンプルを使用するなど、"問題 1: Microsoft Office SharePoint Server で 1 つのレコードを表示するオプションと制限が複数の値に基づいて"配列の要素に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c9920-150">For example, you can use the following code sample in step 3 in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values” to assign values to array elements.</span></span>  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="c9920-151">複合型のパラメーターに NULL 値を指定することで問題 3: 制限</span><span class="sxs-lookup"><span data-stu-id="c9920-151">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="c9920-152">**説明**: Microsoft Office SharePoint Server で、Web パーツからの複合型パラメーターのすべての値を指定しないと場合、NULL として渡す必要複合型のパラメーターの値、WCF サービスにします。</span><span class="sxs-lookup"><span data-stu-id="c9920-152">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="c9920-153">ただし、NULL 以外の値が、複合型パラメーターに渡され、単純型の場合は、その子要素に対して NULL が渡されました。</span><span class="sxs-lookup"><span data-stu-id="c9920-153">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="c9920-154">これにより、予期されるメッセージ スキーマと WCF サービスに渡されるメッセージ スキーマの不一致が原因です。</span><span class="sxs-lookup"><span data-stu-id="c9920-154">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="c9920-155">その結果、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エラー メッセージを表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9920-155">As a result, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9920-156">Microsoft Office SharePoint Server での Web パーツから値が渡されない場合、複合型パラメーターの既定値を調べるに記載されているコード サンプルでは、手順 2 を使用して"問題 1: Microsoft Office SharePoint Server で 1 つのレコードを表示するオプションと制限基づく複数の値です。"</span><span class="sxs-lookup"><span data-stu-id="c9920-156">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values.”</span></span>  
  
 <span data-ttu-id="c9920-157">**解像度**: 複合型パラメーターに NULL 値を割り当てるカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9920-157">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter.</span></span> <span data-ttu-id="c9920-158">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [SAP アダプタでカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9920-158">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9920-159">参照</span><span class="sxs-lookup"><span data-stu-id="c9920-159">See Also</span></span>  
[<span data-ttu-id="c9920-160">SharePoint での SAP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9920-160">Use the SAP adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)