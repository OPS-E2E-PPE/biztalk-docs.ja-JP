---
title: SharePoint で SAP アダプターの使用時の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d310741-b648-4028-a75f-35b843edcc8d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6582b211de7ace113a50e09235bae0cb9eea8dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373580"
---
# <a name="considerations-when-using-the-sap-adapter-with-sharepoint"></a><span data-ttu-id="df062-102">SharePoint で SAP アダプターの使用時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="df062-102">Considerations when using the SAP adapter with SharePoint</span></span>
<span data-ttu-id="df062-103">このトピックでには使用中に発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="df062-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="df062-104">問題は、2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="df062-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="df062-105">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="df062-105">General issues</span></span>  
  
-   <span data-ttu-id="df062-106">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="df062-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="df062-107">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="df062-107">General Issues</span></span>  
 <span data-ttu-id="df062-108">このセクションには、解像度を持たないか、アプリケーション定義ファイルの解像度を変更する必要がありますいずれかの問題が含まれています。</span><span class="sxs-lookup"><span data-stu-id="df062-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="df062-109">問題 1:WCF サービスによって返される単純型のデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="df062-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="df062-110">**説明**:Microsoft Office SharePoint Server には、データセットまたはコレクション型のみにする WCF サービスによって返されるデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="df062-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="df062-111">単純型の WCF サービスによって返されるデータは、Microsoft Office SharePoint Server では、データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="df062-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="df062-112">**解像度**:解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="df062-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="df062-113">Microsoft Office SharePoint Server に関する既知の問題になります。</span><span class="sxs-lookup"><span data-stu-id="df062-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="df062-114">問題 2:WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df062-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="df062-115">**説明**:WCF サービスによって返されるデータが NULL 値の場合、Microsoft Office SharePoint Server には、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df062-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="df062-116">たとえばのビジネス データ一覧 Web パーツを使用している、 **Finder**メソッド、インスタンス化し、検索式に基づく SAP システムで顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="df062-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the SAP system based on a search expression.</span></span> <span data-ttu-id="df062-117">指定した検索式は、NULL 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="df062-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="df062-118">この場合は、Microsoft Office SharePoint Server、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df062-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="df062-119">**解像度**:解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="df062-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="df062-120">Microsoft Office SharePoint Server に関する既知の問題になります。</span><span class="sxs-lookup"><span data-stu-id="df062-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="df062-121">問題 3:WCF サービスによって返される単純型の配列は表示されません。</span><span class="sxs-lookup"><span data-stu-id="df062-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="df062-122">**説明**:WCF サービスによって返されるデータが単純型の配列の場合は、Microsoft Office SharePoint Server では、データが表示されません。</span><span class="sxs-lookup"><span data-stu-id="df062-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="df062-123">さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます。「バックエンド システムのアダプターから構造体 (MethodInstance、パラメーターまたは TypeDescriptor) に対応するメタデータと互換性がありません。」</span><span class="sxs-lookup"><span data-stu-id="df062-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="df062-124">**解像度**:解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="df062-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="df062-125">Microsoft Office SharePoint Server およびビジネス データ カタログ定義エディターでの既知の制限事項になります。</span><span class="sxs-lookup"><span data-stu-id="df062-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="df062-126">問題 4:300 を超えるフィールドを持つ複合型パラメーターを含むアプリケーション定義ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="df062-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="df062-127">**説明**:Microsoft Office SharePoint Server は、WCF サービスによって返された複合型パラメーターの 300 を超えるフィールドがあり、これを行うにしようとするとエラー メッセージが表示されるアプリケーション定義ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="df062-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="df062-128">これは、複合型のパラメーターの 300 を超えるフィールドを表示することができない、Microsoft Office SharePoint Server の制限のため。</span><span class="sxs-lookup"><span data-stu-id="df062-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="df062-129">**解像度**:ビジネス データ カタログ定義エディターを使用すると、300 未満の複合型のパラメーターのフィールドの数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="df062-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="df062-130">お客様の要件に応じて、ビジネス データ カタログ定義エディターで Microsoft Office SharePoint Server に表示される必要としない複合型のパラメーターのフィールドを削除できます。</span><span class="sxs-lookup"><span data-stu-id="df062-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="df062-131">またはも、すべてのフィールドと共に、アプリケーション定義ファイル キーをビジネス データ カタログ定義エディターからエクスポートし、メモ帳などないフィールドを削除する XML 作成アプリケーションでのアプリケーション定義ファイルを変更し、300 にフィールドの数を制限するために必要です。</span><span class="sxs-lookup"><span data-stu-id="df062-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <a name="Custom_Web_Part"></a> <span data-ttu-id="df062-132">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="df062-132">Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="df062-133">このセクションには、解決するためのカスタム Web パーツを使用する必要のある問題が含まれています。</span><span class="sxs-lookup"><span data-stu-id="df062-133">This section contains issues that require the use of custom Web Part for a resolution.</span></span> <span data-ttu-id="df062-134">カスタム Web パーツを使用して、操作中に思いつくの問題を解決する方法については詳細な[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]および Microsoft Office SharePoint Server を参照してください[SAP アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="df062-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span>  
  
###  <a name="Issue1"></a> <span data-ttu-id="df062-135">問題 1:複数の値に基づいて、1 つのレコードを表示する Microsoft Office SharePoint Server での制限事項</span><span class="sxs-lookup"><span data-stu-id="df062-135">Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="df062-136">**説明**:SAP システムから複数の値 (入力パラメーター) に基づく Microsoft Office SharePoint Server で 1 つのレコードを表示する場合で指定された 3 つの Web パーツ (ビジネス データ一覧、ビジネス データ項目、およびビジネス データ関連一覧) のいずれかを使用できません。[手順 3。SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)で[チュートリアル 1。SharePoint サイト上の SAP システムからのデータ表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="df062-136">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from an SAP system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="df062-137">**解像度**:これを行うには、カスタム Web パーツを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df062-137">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="df062-138">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [SAP アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="df062-138">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span> <span data-ttu-id="df062-139">"手順 1。カスタム Web パーツの作成"のトピック、手順 5. で、次のコード サンプルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="df062-139">In “Step 1: Create a Custom Web Part” of that topic, you can use the following code sample in step 5.</span></span> <span data-ttu-id="df062-140">次のコード サンプルは BankCountry と BankKey、入力パラメーターとして受け取り、Microsoft Office SharePoint Server の 1 つのレコードとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="df062-140">The following code sample takes BankCountry and BankKey as the input parameters, and then displays them as a single record in Microsoft Office SharePoint Server.</span></span>  
  
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
>  <span data-ttu-id="df062-141">アプリケーション定義ファイルを含める必要があります、 **Specificfinder**メソッドのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="df062-141">The application definition file must contain the **Specific Finder** method instance.</span></span> <span data-ttu-id="df062-142">A **Specificfinder**メソッド識別子に基づいて特定のレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="df062-142">A **Specific Finder** method finds a specific record based on an identifier.</span></span> <span data-ttu-id="df062-143">作成する方法については、 **Specificfinder**メソッドのインスタンスを参照してください"要件 2。詳細を取得、顧客の一覧から特定の顧客"で[手順 2。SAP アイテム用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)で[チュートリアル 1。SharePoint サイト上の SAP システムからのデータ表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="df062-143">For information about creating a **Specific Finder** method instance, see “Requirement 2: Retrieve Details for a Specific Customer from the List of Customers” in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="df062-144">問題 2:配列の要素に値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="df062-144">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="df062-145">**説明**:WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列要素の値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="df062-145">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="df062-146">できませんまたは使用すること、ビジネス データ一覧ビジネス データ項目の Web パーツでは、Microsoft Office SharePoint Server の WCF サービスに入力パラメーター (配列の要素) の値を指定することがわかります。</span><span class="sxs-lookup"><span data-stu-id="df062-146">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="df062-147">これは、配列は、アプリケーション定義ファイルで定義されている方法が原因です。</span><span class="sxs-lookup"><span data-stu-id="df062-147">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="df062-148">**解像度**:配列の要素に値を割り当てるには、カスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="df062-148">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="df062-149">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [SAP アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="df062-149">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span> <span data-ttu-id="df062-150">たとえば、手順 3 で次のコード サンプルを使用することができます"問題 1。Microsoft Office SharePoint Server での 1 つのレコードの表示の制限事項は、複数の値に基づく"配列の要素に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df062-150">For example, you can use the following code sample in step 3 in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values” to assign values to array elements.</span></span>  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="df062-151">問題 3:複合型のパラメーターに NULL 値を指定すると制限</span><span class="sxs-lookup"><span data-stu-id="df062-151">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="df062-152">**説明**:Microsoft Office SharePoint Server では、Web パーツから複合型のパラメーターの値を指定しない場合は NULL する必要があります複合型のパラメーターの値としてに渡す WCF サービス。</span><span class="sxs-lookup"><span data-stu-id="df062-152">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="df062-153">ただし、複合型のパラメーターの NULL 以外の値が渡され、(単純型) の場合は、その子要素の NULL が渡されます。</span><span class="sxs-lookup"><span data-stu-id="df062-153">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="df062-154">これにより、適切なメッセージ スキーマと、WCF サービスに渡されるメッセージ スキーマが一致しません。</span><span class="sxs-lookup"><span data-stu-id="df062-154">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="df062-155">結果として、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エラー メッセージを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="df062-155">As a result, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df062-156">Microsoft Office SharePoint Server での Web パーツから値が渡されないときに、複合型のパラメーターの既定値を確認するで説明されているコード サンプルでは、手順 2 を使用して"問題 1。Microsoft Office SharePoint Server での 1 つのレコードの表示の制限に基づく複数の値。"</span><span class="sxs-lookup"><span data-stu-id="df062-156">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values.”</span></span>  
  
 <span data-ttu-id="df062-157">**解像度**:カスタム Web パーツを使用して、複合型パラメーターに NULL 値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df062-157">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter.</span></span> <span data-ttu-id="df062-158">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [SAP アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="df062-158">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df062-159">参照</span><span class="sxs-lookup"><span data-stu-id="df062-159">See Also</span></span>  
[<span data-ttu-id="df062-160">SharePoint で SAP アダプターを使用する</span><span class="sxs-lookup"><span data-stu-id="df062-160">Use the SAP adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)