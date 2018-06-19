---
title: SharePoint で Siebel アダプターの使用時の考慮事項 |Microsoft ドキュメント
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
ms.openlocfilehash: 1df22d3eb20dc6286d5b85c3648db98518f23e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223922"
---
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a><span data-ttu-id="33546-102">SharePoint で Siebel アダプターの使用時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="33546-102">Considerations when using the Siebel adapter with SharePoint</span></span>
<span data-ttu-id="33546-103">このトピックの内容には使用しているときに発生する可能性の問題に関する情報が含まれています、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]解像度と共に、Microsoft Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="33546-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="33546-104">問題は、2 つのカテゴリに分けられます。</span><span class="sxs-lookup"><span data-stu-id="33546-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="33546-105">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="33546-105">General issues</span></span>  
  
-   <span data-ttu-id="33546-106">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="33546-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="33546-107">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="33546-107">General Issues</span></span>  
 <span data-ttu-id="33546-108">このセクションには、問題解決が必要ないか、アプリケーション定義ファイルの解像度を変更する必要がありますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="33546-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="33546-109">問題 1: WCF サービスによって返される単純型のデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="33546-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="33546-110">**説明**: Microsoft Office SharePoint Server は、データセットまたはコレクションの型だけにする WCF サービスによって返されるデータを期待します。</span><span class="sxs-lookup"><span data-stu-id="33546-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="33546-111">WCF サービスによって返されるデータが単純型である場合、Microsoft Office SharePoint Server では、データが表示されません。</span><span class="sxs-lookup"><span data-stu-id="33546-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="33546-112">**解像度**: 解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="33546-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="33546-113">これは、Microsoft Office SharePoint Server に関する既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="33546-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="33546-114">問題 2: WCF サービスによって返されるデータが NULL の場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33546-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="33546-115">**説明**: WCF サービスによって返されるデータが NULL 値の場合は、Microsoft Office SharePoint Server がエラー メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="33546-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="33546-116">たとえば、ビジネス データ一覧 Web パーツを使用している、 **Finder**メソッドをインスタンス化、および検索式に基づく Siebel システムで顧客の検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="33546-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the Siebel system based on a search expression.</span></span> <span data-ttu-id="33546-117">指定した検索式では、NULL 値をフェッチします。</span><span class="sxs-lookup"><span data-stu-id="33546-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="33546-118">この例では、Microsoft Office SharePoint Server、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33546-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="33546-119">**解像度**: 解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="33546-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="33546-120">これは、Microsoft Office SharePoint Server に関する既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="33546-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="33546-121">問題 3: WCF サービスによって返される単純型の配列は表示されません。</span><span class="sxs-lookup"><span data-stu-id="33546-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="33546-122">**説明**: Microsoft Office SharePoint Server にデータが表示されない場合は、WCF サービスによって返されるデータが単純型の配列。</span><span class="sxs-lookup"><span data-stu-id="33546-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="33546-123">さらに、ビジネス データ カタログ定義エディターでの単純型の配列を返すメソッドのインスタンスを実行するときに、次のエラー メッセージが表示されます:"システム アダプターがバックエンド返された構造体、対応するメタデータ (と互換性がありませんMethodInstance、パラメーターまたは TypeDescriptor)。"</span><span class="sxs-lookup"><span data-stu-id="33546-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="33546-124">**解像度**: 解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="33546-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="33546-125">Microsoft Office SharePoint Server とビジネス データ カタログ定義エディターで、既知の制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33546-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="33546-126">問題 4: が 300 を超えるフィールドを持つ複合型パラメーターを含んでいるアプリケーション定義ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="33546-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="33546-127">**説明**: Microsoft Office SharePoint Server が WCF サービスによって返される、複合型パラメーターで 300 を超えるフィールドがあり、これを行うにしようとすると、エラー メッセージを表示するアプリケーション定義ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="33546-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="33546-128">これは、複合型パラメーターの 300 を超えるフィールドを表示することはできませんの Microsoft Office SharePoint Server の制限のためです。</span><span class="sxs-lookup"><span data-stu-id="33546-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="33546-129">**解像度**: エディターを使用して、ビジネス データ カタログ定義 300 未満に複合型パラメーターのフィールドの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="33546-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="33546-130">必要に応じての複合型パラメーターで、ビジネス データ カタログ定義エディターするを必要としない Microsoft Office SharePoint Server に表示されるフィールドを削除できます。</span><span class="sxs-lookup"><span data-stu-id="33546-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="33546-131">代わりに、エクスポートも、アプリケーション定義ファイル ビジネス データ カタログ定義エディターからすべてのフィールドがおよび、メモ帳などされていないフィールドを削除する XML オーサリング アプリケーションで、アプリケーション定義ファイルを変更できます。300 にフィールドの数を制限するために必要です。</span><span class="sxs-lookup"><span data-stu-id="33546-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <a name="Custom_Web_Part"></a><span data-ttu-id="33546-132">カスタム Web パーツに関連する問題</span><span class="sxs-lookup"><span data-stu-id="33546-132">Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="33546-133">このセクションには、問題解決するためのカスタム Web パーツの使用を必要とするにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="33546-133">This section contains issues that require the use of custom Web Parts for resolution.</span></span> <span data-ttu-id="33546-134">詳細については、使用中に生じる可能性があります問題を解決するのには、カスタム Web パーツを使用して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]および Microsoft Office SharePoint Server を参照してください[Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="33546-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a><span data-ttu-id="33546-135">問題 1: 列挙子のインデックスは、列挙型のデータ型の値の代わりに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33546-135">Issue 1: Index of an enumerator is displayed instead of the value for the enum data type</span></span>  
 <span data-ttu-id="33546-136">**説明**: 列挙子のインデックスは、ビジネス データ一覧または Microsoft Office SharePoint Server でビジネス データ項目 Web パーツには列挙型 (が特殊な種類の列挙子と呼ばれる名前付き定数のセットで構成される) のデータがある場合Microsoft Office SharePoint Server でその値の代わりに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33546-136">**Explanation**: If a Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server contains data of enum type (a distinct type consisting of a set of named constants called the enumerators), the index of the enumerator is displayed instead of its value in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="33546-137">これは、ため、ビジネス データ一覧とビジネス データ項目 Web パーツを正しく印刷いない SharePoint ポータルに、列挙型のデータの値です。</span><span class="sxs-lookup"><span data-stu-id="33546-137">This is because the Business Data List and Business Data Item Web Parts incorrectly print the values of the enum type data to the SharePoint portal.</span></span>  
  
 <span data-ttu-id="33546-138">**解像度**: インデックスではなく、列挙子の値を出力するカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="33546-138">**Resolution**: Use a custom Web Part to print the value of the enumerator instead of the index.</span></span> <span data-ttu-id="33546-139">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="33546-139">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="33546-140">たとえば、Microsoft Office SharePoint Server に列挙型のデータの正しい値を印刷するのに Web パーツで次のコード サンプルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="33546-140">For example, you can use the following code sample in your Web part to print the correct values of enum type data on Microsoft Office SharePoint Server.</span></span>  
  
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
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="33546-141">問題 2: 配列の要素に値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="33546-141">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="33546-142">**説明**: WCF サービスの入力パラメーターが配列の場合は、ビジネス データ カタログ定義エディターを使用して作成されたアプリケーション定義ファイルで定義されているフィルターを使用して配列の要素に値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="33546-142">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="33546-143">使用することできませんビジネス データ一覧またはビジネス データ項目の Web パーツ Microsoft Office SharePoint Server でこれらの入力パラメーター (配列の要素) WCF サービスへの値を指定を意味します。</span><span class="sxs-lookup"><span data-stu-id="33546-143">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="33546-144">これは、配列が、アプリケーション定義ファイルで定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="33546-144">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="33546-145">**解像度**: 配列要素に値を割り当てるカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="33546-145">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="33546-146">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="33546-146">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="33546-147">手順 3 で、次のコード サンプルを使用するなど、"問題 1: 列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"配列の要素に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="33546-147">For example, you can use the following code sample in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” to assign values to array elements.</span></span>  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="33546-148">複合型のパラメーターに NULL 値を指定することで問題 3: 制限</span><span class="sxs-lookup"><span data-stu-id="33546-148">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="33546-149">**説明**: Microsoft Office SharePoint Server で、Web パーツからの複合型パラメーターのすべての値を指定しないと場合、NULL として渡す必要複合型のパラメーターの値、WCF サービスにします。</span><span class="sxs-lookup"><span data-stu-id="33546-149">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="33546-150">ただし、NULL 以外の値が、複合型パラメーターに渡され、単純型の場合は、その子要素に対して NULL が渡されました。</span><span class="sxs-lookup"><span data-stu-id="33546-150">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="33546-151">これにより、予期されるメッセージ スキーマと WCF サービスに渡されるメッセージ スキーマの不一致が原因です。</span><span class="sxs-lookup"><span data-stu-id="33546-151">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="33546-152">その結果、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]エラー メッセージを表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="33546-152">As a result, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33546-153">Microsoft Office SharePoint Server での Web パーツから値が渡されない場合、複合型パラメーターの既定値を調べるに記載されているコード サンプルでは、手順 2 を使用して"問題 1: 列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"。</span><span class="sxs-lookup"><span data-stu-id="33546-153">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type.”</span></span>  
  
 <span data-ttu-id="33546-154">**解像度**: Microsoft Office SharePoint Server での Web パーツから値が指定されていない場合、複合型パラメーターに NULL 値を割り当てるカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="33546-154">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter when no value is specified from a Web Part in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="33546-155">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="33546-155">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
###  <a name="Issue1"></a><span data-ttu-id="33546-156">問題 4: 複数の値に基づいて Microsoft Office SharePoint Server で 1 つのレコードを表示するオプションと制限</span><span class="sxs-lookup"><span data-stu-id="33546-156">Issue 4: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="33546-157">**説明**: Microsoft Office SharePoint server、Siebel システムから複数の値 (入力パラメーター) に基づく 1 つのレコードを表示する場合は、次の 3 つの Web パーツ (のビジネス データ一覧、ビジネス データ項目、および Business のいずれかを使用できません指定されたデータ関連一覧)[手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)で[チュートリアル 1: 提示データ Siebel システムから SharePoint サイトで](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)です。</span><span class="sxs-lookup"><span data-stu-id="33546-157">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from a Siebel system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) in [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="33546-158">**解像度**: これを行うカスタム Web パーツを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33546-158">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="33546-159">カスタム Web パーツの使用方法の詳細については、次を参照してください。 [Siebel アダプターとカスタム Web パーツを使用して](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="33546-159">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="33546-160">たとえば、手順 3 で"問題 1: 列挙型のデータ型の値ではなく、列挙子のインデックスが表示されます"1 つのビジネス コンポーネントのパラメーターへの入力を提供する代わりに 1 つ以上のパラメーターの値を指定するコードを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="33546-160">For example, in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” you can modify the code to provide values for more than one parameter instead of providing input to a single business component parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33546-161">参照</span><span class="sxs-lookup"><span data-stu-id="33546-161">See Also</span></span>  
 [<span data-ttu-id="33546-162">SharePoint での Siebel アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="33546-162">Use the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)