---
title: "インスタンス (EDI) の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cceea8afe67f7e69b3ee842198d9a5373a972d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validating-an-instance-edi"></a><span data-ttu-id="fac57-102">インスタンスの検証 (EDI)</span><span class="sxs-lookup"><span data-stu-id="fac57-102">Validating an Instance (EDI)</span></span>
<span data-ttu-id="fac57-103">デザイン時にインスタンスを EDI スキーマに対して検証することができます。</span><span class="sxs-lookup"><span data-stu-id="fac57-103">You can validate an instance against its EDI schema at design time.</span></span> <span data-ttu-id="fac57-104">それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。</span><span class="sxs-lookup"><span data-stu-id="fac57-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="fac57-105">検証するインスタンスは、単一のトランザクション セット (インターチェンジとグループ ヘッダーなし)、単一のトランザクション セットを持つインターチェンジ (インターチェンジとグループ ヘッダーあり)、複数のトランザクション セットを持つ完全なバッチ処理されたインターチェンジ (インターチェンジとグループ ヘッダーあり) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="fac57-105">The instance that you validate can be a single transaction set (without interchange and group headers), an interchange with a single transaction set (with interchange and group headers), or a complete batched interchange with multiple transaction sets (with interchange and group headers).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fac57-106">XML に保存されたインターチェンジの検証はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fac57-106">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="fac57-107">しかし、EDI に保存されたインターチェンジの検証はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fac57-107">However, validation of an EDI preserved interchange is supported.</span></span>  
  
 <span data-ttu-id="fac57-108">インスタンス検証操作は、EDI と XSD の検証を行います。</span><span class="sxs-lookup"><span data-stu-id="fac57-108">The validate-instance operation performs both EDI and XSD validation.</span></span>  
  
 <span data-ttu-id="fac57-109">インスタンスを検証するとき、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、区切り記号や構文識別子など、そのインスタンスの中で検証する構成を指定するダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fac57-109">When you validate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration to be validated in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fac57-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="fac57-110">Prerequisites</span></span>  
 <span data-ttu-id="fac57-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fac57-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-an-instance-against-its-schema"></a><span data-ttu-id="fac57-112">インスタンスをスキーマに対して検証するには</span><span class="sxs-lookup"><span data-stu-id="fac57-112">To validate an instance against its schema</span></span>  
  
1.  <span data-ttu-id="fac57-113">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="fac57-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span>  
  
2.  <span data-ttu-id="fac57-114">ソリューション エクスプローラーで、メッセージ インスタンスに必要なすべてのスキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="fac57-114">In Solution Explorer, add to the project all schemas required for the message instance.</span></span>  
  
    1.  <span data-ttu-id="fac57-115">インターチェンジやグループ ヘッダーを持たない単一のトランザクション セットを検証するときは、そのトランザクション セットのドキュメント スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="fac57-115">If you are validating a single transaction set without interchange and group headers, add the document schema for that transaction set.</span></span>  
  
    2.  <span data-ttu-id="fac57-116">単一のトランザクション セットを持つインターチェンジを検証するときは、そのトランザクションのスキーマと、メッセージで使用するエンコードの種類に対するバッチ スキーマ ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 内の Edifact_BatchSchema.xsd または X12_BatchSchema.xsd のどちらか) をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="fac57-116">If you are validating an interchange with a single transaction set, add to the project the schema for the transaction and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fac57-117">インスタンスのエンベロープを検証するには、バッチ スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="fac57-117">The batch schema is required to validate the envelope of the instance.</span></span> <span data-ttu-id="fac57-118">メッセージ スキーマのみを使用する場合、エンベロープは検証されません。</span><span class="sxs-lookup"><span data-stu-id="fac57-118">If you were to use only the message schema, the envelope would not be validated.</span></span>  
  
    3.  <span data-ttu-id="fac57-119">複数のトランザクション セットを持つバッチ インターチェンジを検証するときは、メッセージ インスタンス中の各トランザクション セット グループに対するスキーマと、メッセージで使用するエンコードの種類に対するバッチ スキーマ ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 内の Edifact_BatchSchema.xsd または X12_BatchSchema.xsd のどちらか) をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="fac57-119">If you are validating a batched interchange with multiple transaction sets, add to the project the schemas for each transaction set group in the message instance, and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fac57-120">サービス スキーマをカスタマイズした場合は、ドキュメント (トランザクション セット) スキーマと、必要に応じてバッチ スキーマに加え、カスタム サービス スキーマを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="fac57-120">If you have customized the service schema, you will have to include the custom service schema in the BizTalk project, in addition to the document (transaction set) schema(s) and if necessary, the batch schema.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fac57-121">インスタンスを検証するためにプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fac57-121">You do not have to build the project to validate an instance.</span></span>  
  
3.  <span data-ttu-id="fac57-122">以下のようにして、ソリューション エクスプローラーでスキーマのプロパティ ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="fac57-122">Display the property page for the schema in Solution Explorer, as follows:</span></span>  
  
    1.  <span data-ttu-id="fac57-123">単一のトランザクション セットを検証するときは、そのトランザクション セットのドキュメント スキーマを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-123">If you are validating a single transaction set, right-click the document schema for that transaction set, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="fac57-124">単一のトランザクション セットを持つインターチェンジまたは複数のトランザクション セットを持つバッチ インターチェンジを検証している場合、バッチ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd schema) を右クリックし、をクリックして**のプロパティ**.</span><span class="sxs-lookup"><span data-stu-id="fac57-124">If you are validating an interchange with a single transaction set or a batched interchange with multiple transaction sets, right-click the batch schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd schema), and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="fac57-125">スキーマのプロパティ ウィンドウでの**入力インスタンス ファイル名**検証、またはファイルを参照して選択し、をクリックしたいメッセージ インスタンスのパスと名前を入力**OK**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-125">In Properties window for the schema, for **Input Instance Filename** enter the name and path of the message instance that you want to validate, or browse to the file, select it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="fac57-126">**インスタンスの入力の種類の検証**を検証するファイルの種類を入力:**ネイティブ**EDI ファイルのまたは**XML** XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="fac57-126">For **Validate Instance Input Type**, enter the type of the file to be validate: **Native** for a EDI file or **XML** for an XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fac57-127">XML に保存されたインターチェンジの検証はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fac57-127">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="fac57-128">XML を選択した場合、**インスタンスの入力の種類の検証**保存されたインターチェンジを検証するときに、プロパティは、操作が失敗し、nothing が返されます。</span><span class="sxs-lookup"><span data-stu-id="fac57-128">If you select XML for the **Validate Instance Input Type** property when validating a preserved interchange, the operation will fail and nothing will be returned.</span></span> <span data-ttu-id="fac57-129">ただし、選択した場合**ネイティブ**の**インスタンスの入力の種類の検証**保存されたインターチェンジを検証する場合、操作は成功します。</span><span class="sxs-lookup"><span data-stu-id="fac57-129">However, if you select **Native** for the **Validate Instance Input Type** when validating a preserved interchange, the operation will succeed.</span></span>  
  
6.  <span data-ttu-id="fac57-130">メッセージ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd の 1 つのトランザクション セットを持つインターチェンジまたはバッチ インターチェンジを検証する場合) を右クリックし、をクリックして**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-130">Right-click the message schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd if validating an interchange with a single transaction set or a batched interchange) and then click **Validate Instance**.</span></span>  
  
7.  <span data-ttu-id="fac57-131">**EDI インスタンスのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="fac57-131">In the **EDI Instance Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="fac57-132">インスタンスは、繰り返し区切り記号を使用する場合は、選択**繰り返し区切り記号**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-132">If your instance should use a repetition separator, select **Repetition separator**.</span></span>  
  
    2.  <span data-ttu-id="fac57-133">インスタンスは、末尾の区切り記号を使用する場合は、選択**はい**の**末尾の区切り記号を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-133">If your instance should use trailing delimiters, select **Yes** for **Use trailing delimiters**.</span></span>  
  
    3.  <span data-ttu-id="fac57-134">インスタンスが必要があります以外の文字を使用するかどうかは**基本的な****拡張**または**Unicode**で**構文識別子**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-134">If your instance should use a character set other than **Basic**, select **Extended** or **Unicode** in **Syntax identifier**.</span></span>  
  
    4.  <span data-ttu-id="fac57-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fac57-135">Click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fac57-136">**EDI インスタンスのプロパティ** ダイアログ ボックスが 2 回クリックした後に表示される**OK**です。</span><span class="sxs-lookup"><span data-stu-id="fac57-136">The **EDI Instance Properties** dialog box might appear a second time after you have clicked **OK**.</span></span> <span data-ttu-id="fac57-137">場合は、クリックして**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="fac57-137">If so, click **OK** again.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fac57-138">**EDI インスタンスのプロパティ** ダイアログ ボックスが、同じログインしているユーザーに対して実行された最後のインスタンス検証操作で使用する同じ値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fac57-138">The **EDI Instance Properties** dialog box will be populated with the same values used in the last validate-instance operation that was run for the same logged-in user.</span></span>  
  
8.  <span data-ttu-id="fac57-139">内のメッセージがあることを確認、**出力**操作が成功したことを示すウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="fac57-139">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac57-140">参照</span><span class="sxs-lookup"><span data-stu-id="fac57-140">See Also</span></span>  
 <span data-ttu-id="fac57-141">[デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fac57-141">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="fac57-142">インスタンス (EDI) の生成</span><span class="sxs-lookup"><span data-stu-id="fac57-142">Generating an Instance (EDI)</span></span>](../core/generating-an-instance-edi.md)