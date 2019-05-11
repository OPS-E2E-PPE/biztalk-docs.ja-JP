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
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a><span data-ttu-id="7cf4e-102">SharePoint で Siebel アダプターの使用時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="7cf4e-102">Considerations when using the Siebel adapter with SharePoint</span></span>
<span data-ttu-id="7cf4e-103">このトピックでには使用中に発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="7cf4e-104">問題は、2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="7cf4e-105">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="7cf4e-105">General issues</span></span>  
  
-   <span data-ttu-id="7cf4e-106">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="7cf4e-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="7cf4e-107">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="7cf4e-107">General Issues</span></span>  
 <span data-ttu-id="7cf4e-108">このセクションには、解像度を持たないか、アプリケーション定義ファイルの解像度を変更する必要がありますいずれかの問題が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="7cf4e-109">問題 1:WCF サービスによって返される単純型のデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="7cf4e-110">**説明**:Microsoft Office SharePoint Server には、データセットまたはコレクション型のみにする WCF サービスによって返されるデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="7cf4e-111">単純型の WCF サービスによって返されるデータは、Microsoft Office SharePoint Server では、データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="7cf4e-112">**解像度**:解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="7cf4e-113">Microsoft Office SharePoint Server に関する既知の問題になります。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="7cf4e-114">問題 2:WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="7cf4e-115">**説明**:WCF サービスによって返されるデータが NULL 値の場合、Microsoft Office SharePoint Server には、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="7cf4e-116">たとえばのビジネス データ一覧 Web パーツを使用している、 **Finder**メソッド、インスタンス化し、検索式に基づく Siebel システムで顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the Siebel system based on a search expression.</span></span> <span data-ttu-id="7cf4e-117">指定した検索式は、NULL 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="7cf4e-118">この場合は、Microsoft Office SharePoint Server、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="7cf4e-119">**解像度**:解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="7cf4e-120">Microsoft Office SharePoint Server に関する既知の問題になります。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="7cf4e-121">問題 3:WCF サービスによって返される単純型の配列は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="7cf4e-122">**説明**:WCF サービスによって返されるデータが単純型の配列の場合は、Microsoft Office SharePoint Server では、データが表示されません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="7cf4e-123">さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます。「バックエンド システムのアダプターから構造体 (MethodInstance、パラメーターまたは TypeDescriptor) に対応するメタデータと互換性がありません。」</span><span class="sxs-lookup"><span data-stu-id="7cf4e-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="7cf4e-124">**解像度**:解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="7cf4e-125">Microsoft Office SharePoint Server およびビジネス データ カタログ定義エディターでの既知の制限事項になります。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="7cf4e-126">問題 4:300 を超えるフィールドを持つ複合型パラメーターを含むアプリケーション定義ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="7cf4e-127">**説明**:Microsoft Office SharePoint Server は、WCF サービスによって返された複合型パラメーターの 300 を超えるフィールドがあり、これを行うにしようとするとエラー メッセージが表示されるアプリケーション定義ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="7cf4e-128">これは、複合型のパラメーターの 300 を超えるフィールドを表示することができない、Microsoft Office SharePoint Server の制限のため。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="7cf4e-129">**解像度**:ビジネス データ カタログ定義エディターを使用すると、300 未満の複合型のパラメーターのフィールドの数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="7cf4e-130">お客様の要件に応じて、ビジネス データ カタログ定義エディターで Microsoft Office SharePoint Server に表示される必要としない複合型のパラメーターのフィールドを削除できます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="7cf4e-131">またはも、すべてのフィールドと共に、アプリケーション定義ファイル キーをビジネス データ カタログ定義エディターからエクスポートし、メモ帳などないフィールドを削除する XML 作成アプリケーションでのアプリケーション定義ファイルを変更し、300 にフィールドの数を制限するために必要です。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <a name="Custom_Web_Part"></a> <span data-ttu-id="7cf4e-132">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="7cf4e-132">Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="7cf4e-133">このセクションには、問題解決するため、カスタム Web パーツの使用を必要とするにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-133">This section contains issues that require the use of custom Web Parts for resolution.</span></span> <span data-ttu-id="7cf4e-134">カスタム Web パーツを使用して、操作中に思いつくの問題を解決する方法については詳細な[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]および Microsoft Office SharePoint Server を参照してください[Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a><span data-ttu-id="7cf4e-135">問題 1:列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-135">Issue 1: Index of an enumerator is displayed instead of the value for the enum data type</span></span>  
 <span data-ttu-id="7cf4e-136">**説明**:ビジネス データ一覧または Microsoft Office SharePoint Server では、ビジネス データ項目 Web パーツには、列挙型 (列挙子と呼ばれる名前付き定数のセットで構成される異なる型) のデータが含まれている、列挙子のインデックスはでは、その値の代わりに表示されます。Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-136">**Explanation**: If a Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server contains data of enum type (a distinct type consisting of a set of named constants called the enumerators), the index of the enumerator is displayed instead of its value in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="7cf4e-137">これは、ため、ビジネス データ一覧とビジネス データ項目の Web パーツを正しく印刷しない SharePoint ポータルに列挙型のデータの値です。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-137">This is because the Business Data List and Business Data Item Web Parts incorrectly print the values of the enum type data to the SharePoint portal.</span></span>  
  
 <span data-ttu-id="7cf4e-138">**解像度**:インデックスではなく、列挙子の値を出力するのにには、カスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-138">**Resolution**: Use a custom Web Part to print the value of the enumerator instead of the index.</span></span> <span data-ttu-id="7cf4e-139">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-139">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="7cf4e-140">たとえば、Microsoft Office SharePoint Server に列挙型のデータの正しい値を印刷するのに Web パーツで次のコード サンプルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-140">For example, you can use the following code sample in your Web part to print the correct values of enum type data on Microsoft Office SharePoint Server.</span></span>  
  
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
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="7cf4e-141">問題 2:配列の要素に値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-141">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="7cf4e-142">**説明**:WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列要素の値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-142">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="7cf4e-143">できませんまたは使用すること、ビジネス データ一覧ビジネス データ項目の Web パーツでは、Microsoft Office SharePoint Server の WCF サービスに入力パラメーター (配列の要素) の値を指定することがわかります。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-143">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="7cf4e-144">これは、配列は、アプリケーション定義ファイルで定義されている方法が原因です。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-144">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="7cf4e-145">**解像度**:配列の要素に値を割り当てるには、カスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-145">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="7cf4e-146">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-146">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="7cf4e-147">たとえば、手順 3 で次のコード サンプルを使用することができます"問題 1。列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"配列の要素に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-147">For example, you can use the following code sample in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” to assign values to array elements.</span></span>  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="7cf4e-148">問題 3:複合型のパラメーターに NULL 値を指定すると制限</span><span class="sxs-lookup"><span data-stu-id="7cf4e-148">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="7cf4e-149">**説明**:Microsoft Office SharePoint Server では、Web パーツから複合型のパラメーターの値を指定しない場合は NULL する必要があります複合型のパラメーターの値としてに渡す WCF サービス。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-149">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="7cf4e-150">ただし、複合型のパラメーターの NULL 以外の値が渡され、(単純型) の場合は、その子要素の NULL が渡されます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-150">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="7cf4e-151">これにより、適切なメッセージ スキーマと、WCF サービスに渡されるメッセージ スキーマが一致しません。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-151">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="7cf4e-152">結果として、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]エラー メッセージを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-152">As a result, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cf4e-153">Microsoft Office SharePoint Server での Web パーツから値が渡されないときに、複合型のパラメーターの既定値を確認するで説明されているコード サンプルでは、手順 2 を使用して"問題 1。列挙子のインデックスが表示されます、列挙型のデータ型の値の代わりにします。"</span><span class="sxs-lookup"><span data-stu-id="7cf4e-153">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type.”</span></span>  
  
 <span data-ttu-id="7cf4e-154">**解像度**:Microsoft Office SharePoint Server での Web パーツから値が指定されていない場合、複合型のパラメーターに NULL 値を割り当てるには、カスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-154">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter when no value is specified from a Web Part in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="7cf4e-155">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-155">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
###  <a name="Issue1"></a> <span data-ttu-id="7cf4e-156">問題 4:複数の値に基づいて、1 つのレコードを表示する Microsoft Office SharePoint Server での制限事項</span><span class="sxs-lookup"><span data-stu-id="7cf4e-156">Issue 4: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="7cf4e-157">**説明**:Siebel システムから複数の値 (入力パラメーター) に基づく Microsoft Office SharePoint Server で 1 つのレコードを表示する場合は、次の 3 つの Web パーツ (ビジネス データ一覧、ビジネス データ項目、およびビジネス データ関連一覧) のいずれかを指定を使用できません。[手順 3。Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)で[チュートリアル 1。SharePoint サイト上の Siebel システムからのデータを表示する](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-157">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from a Siebel system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) in [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="7cf4e-158">**解像度**:これを行うには、カスタム Web パーツを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-158">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="7cf4e-159">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターを使用したカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-159">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="7cf4e-160">たとえば、手順 3. で"問題 1。列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"と、1 つのビジネス コンポーネントのパラメーターへの入力を提供することではなく 1 つ以上のパラメーターの値を指定するコードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7cf4e-160">For example, in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” you can modify the code to provide values for more than one parameter instead of providing input to a single business component parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf4e-161">参照</span><span class="sxs-lookup"><span data-stu-id="7cf4e-161">See Also</span></span>  
 [<span data-ttu-id="7cf4e-162">SharePoint での Siebel アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="7cf4e-162">Use the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)