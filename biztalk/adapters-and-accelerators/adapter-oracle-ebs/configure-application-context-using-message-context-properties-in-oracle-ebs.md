---
title: Oracle E-business Suite でのメッセージ コンテキスト プロパティを使用してアプリケーション コンテキストの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b76788-5c81-4bb4-8ef6-b1439955ea97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9655d34a1bfce2b82a86c4bf153af940f168095d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375696"
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a><span data-ttu-id="ba026-102">Oracle E-business Suite でのメッセージ コンテキスト プロパティを使用してアプリケーション コンテキストを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba026-102">Configure the application context using message context properties in Oracle E-Business Suite</span></span>
<span data-ttu-id="ba026-103">使用して Oracle E-business Suite の成果物の操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーションのコンテキストを適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba026-103">To perform operations on Oracle E-Business Suite artifacts using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must set the application context appropriately.</span></span> <span data-ttu-id="ba026-104">次の方法では、アプリケーションのコンテキストを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ba026-104">You can set the application context in the following ways:</span></span>  
  
- <span data-ttu-id="ba026-105">アダプターを公開するバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba026-105">By specifying the binding properties that the adapter exposes.</span></span> <span data-ttu-id="ba026-106">詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba026-106">For more information, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
- <span data-ttu-id="ba026-107">アダプターを公開するメッセージ コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba026-107">By using message context properties that the adapter exposes.</span></span> <span data-ttu-id="ba026-108">メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定するときに、次を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba026-108">You must consider the following when setting the application context by using message context properties.</span></span>  
  
  -   <span data-ttu-id="ba026-109">値のみを設定する**ApplicationShortName**、**組織 Id**、 **ResponsibilityKey**、および**ResponsibilityName**を使用してメッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ba026-109">You can set values only for **ApplicationShortName**, **OrganizationID**, **ResponsibilityKey**, and **ResponsibilityName** by using message context properties.</span></span> <span data-ttu-id="ba026-110">ユーザー名とパスワードでは、バインドのプロパティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba026-110">For the user name and password, you must use the binding properties.</span></span> <span data-ttu-id="ba026-111">指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値のオーバーライド、 **ResponsibilityName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ba026-111">The value specified for the **ResponsibilityKey** message context property overrides the value specified for the **ResponsibilityName** message context property.</span></span>  
  
  -   <span data-ttu-id="ba026-112">バインドのプロパティとメッセージ コンテキスト プロパティの両方を使用して、アプリケーションのコンテキストを設定すると、メッセージ コンテキスト プロパティに指定された値は優先され、バインドのプロパティに指定された値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="ba026-112">If you set the application context using both the binding properties and message context properties, the values specified for message context properties take precedence and override the values specified for the binding properties.</span></span> <span data-ttu-id="ba026-113">ただし、たとえば、バインドのプロパティとしてメッセージ コンテキスト プロパティとしてアプリケーションの短い名前と組織の ID および責任の名前を指定する場合、アプリケーションの短い名前の値のみから取得されます、メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ba026-113">However, for example, if you specify the application short name as a message context property, and the organization ID and responsibility name as binding properties, only the value for the application short name is taken from the message context property.</span></span> <span data-ttu-id="ba026-114">残りの部分は関連するバインドのプロパティから取得されます。</span><span class="sxs-lookup"><span data-stu-id="ba026-114">The rest are picked from the relevant binding properties.</span></span>  
  
  <span data-ttu-id="ba026-115">アプリケーションのコンテキストを設定するプロパティをバインド経由でメッセージ コンテキスト プロパティを使用する理由</span><span class="sxs-lookup"><span data-stu-id="ba026-115">Why use message context properties over binding properties to set the application context?</span></span> <span data-ttu-id="ba026-116">Wcf-custom 送信ポート バインドのプロパティを使用して、アプリケーションのコンテキストを設定した場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]特定の組織の ID、責任、およびバインドのプロパティに指定したアプリケーションに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba026-116">If you set the application context using binding properties, the WCF-Custom send port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] can be used only for the specific organization ID, responsibility, and application that you specified for the binding properties.</span></span> <span data-ttu-id="ba026-117">反対に、メッセージ コンテキスト プロパティを使用する場合は、「汎用」の Wcf-custom 送信ポートを構成して、メッセージ レベルで、アプリケーションのコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="ba026-117">On the contrary, if you use the message context property, you can configure a “generic” WCF-Custom send port, and set the application context at the message level.</span></span>  
  
  <span data-ttu-id="ba026-118">アダプター クライアントは、Oracle E-business Suite の操作を呼び出す Oracle E-business Suite に送信されるメッセージのメッセージ コンテキスト プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba026-118">Adapter clients must set the message context properties on the message that is sent to Oracle E-Business Suite to invoke an operation on Oracle E-Business Suite.</span></span> <span data-ttu-id="ba026-119">内のメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は変更できません。</span><span class="sxs-lookup"><span data-stu-id="ba026-119">The messages in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] are immutable.</span></span> <span data-ttu-id="ba026-120">そのため、クライアントは、まず既存のメッセージからメッセージを作成する必要があり、メッセージ コンテキスト プロパティを設定、新しいメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ba026-120">Hence, clients must first create a message from the existing message, and then set the message context properties on the new message.</span></span> <span data-ttu-id="ba026-121">このセクションで説明する手順、既存のメッセージが呼び出されることを想定して**要求**、新しいメッセージが呼び出されたと**New_Request**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-121">For the procedure described in this section, assume that the existing message is called **Request**, and the new message is called **New_Request**.</span></span>  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a><span data-ttu-id="ba026-122">メッセージ コンテキスト プロパティを BizTalk アプリケーションの設定します。</span><span class="sxs-lookup"><span data-stu-id="ba026-122">Set the message context properties for BizTalk applications</span></span>  
  
1. <span data-ttu-id="ba026-123">BizTalk プロジェクトを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ba026-123">Open the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="ba026-124">ソリューション エクスプ ローラーで右クリックして**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-124">In Solution Explorer, right-click **References**, and then click **Add References**.</span></span>  
  
3. <span data-ttu-id="ba026-125">**参照の追加**ダイアログ ボックスで、 をクリックして、**参照**タブをクリックし、場所を参照し、BizTalk プロパティ スキーマ DLL の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は。</span><span class="sxs-lookup"><span data-stu-id="ba026-125">In the **Add Reference** dialog box, click the **Browse** tab, and then browse to the location where the BizTalk property schema DLL for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is available.</span></span>  
  
    <span data-ttu-id="ba026-126">この DLL`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]で\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin です。</span><span class="sxs-lookup"><span data-stu-id="ba026-126">This DLL, `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`, is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] at \<*installation drive*\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin.</span></span>  
  
4. <span data-ttu-id="ba026-127">DLL を選択し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-127">Select the DLL, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="ba026-128">BizTalk オーケストレーションで、メッセージに追加する**New_Request**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-128">In the BizTalk orchestration, add a message, **New_Request**.</span></span> <span data-ttu-id="ba026-129">**メッセージの種類**プロパティ、既存の要求メッセージと同じ型を選択するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ba026-129">For the **Message Type** property, make sure you select the same type as the existing request message.</span></span>  
  
6. <span data-ttu-id="ba026-130">送信図形の前に、送信ポートに送信されるメッセージを使用してメッセージの構築図形を追加し、そのメッセージの割り当て図形中。</span><span class="sxs-lookup"><span data-stu-id="ba026-130">Before the Send shape using which the message is sent to the send port, add a Construct Message shape and within that, a Message Assignment shape.</span></span>  
  
7. <span data-ttu-id="ba026-131">開きますメッセージの割り当て図形をダブルクリックして**BizTalk 式エディタ**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-131">Double-click the Message Assignment shape to open **BizTalk Expression Editor**.</span></span>  
  
8. <span data-ttu-id="ba026-132">**BizTalk 式エディタ**次を追加し、クリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="ba026-132">In **BizTalk Expression Editor**, add the following, and then click **OK**:</span></span>  
  
   ```  
   New_Request = Request;  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ApplicationShortName) = "AR";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityKey) = "RECEIVABLES_VISION_OPERATIONS";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityName) = "Receivables, Vision Operations (USA)";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.OrganizationId) = "204";  
   ```  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="ba026-133">指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値のオーバーライド、 **ResponsibilityName**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ba026-133">The value specified for the **ResponsibilityKey** message context property overrides the value specified for the **ResponsibilityName** message context property.</span></span>  
  
9. <span data-ttu-id="ba026-134">使用して、さらに、オーケストレーションの処理は行われますかどうかを確認、 **New_Request**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ba026-134">Make sure further processing of the orchestration is done by using the **New_Request** message.</span></span>  
  
10. <span data-ttu-id="ba026-135">このオーケストレーションでを展開する前に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]のアセンブリ参照を追加する必要があります`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`オーケストレーションを展開する BizTalk アプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="ba026-135">Before you can deploy this orchestration in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must add the assembly reference for `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll` in the BizTalk application where you will be deploying the orchestration.</span></span> <span data-ttu-id="ba026-136">アセンブリを配置する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ba026-136">To deploy an assembly in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
    1. <span data-ttu-id="ba026-137">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ba026-137">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    2. <span data-ttu-id="ba026-138">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーションでは、します。</span><span class="sxs-lookup"><span data-stu-id="ba026-138">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
    3. <span data-ttu-id="ba026-139">右クリック**リソース**、 をポイント**追加**、 をクリックし、 **BizTalk アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-139">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
    4. <span data-ttu-id="ba026-140">**リソースの追加**ダイアログ ボックスで、をクリックして**追加**、これは、BizTalk アセンブリ ファイルを含むフォルダーに移動します\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin です。</span><span class="sxs-lookup"><span data-stu-id="ba026-140">In the **Add Resources** dialog box, click **Add**, navigate to the folder containing the BizTalk assembly file, which is \<*installation drive*\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin.</span></span> <span data-ttu-id="ba026-141">選択、`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`ファイルを開き、をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-141">Select the `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll` file, and then click **Open**.</span></span>  
  
    5. <span data-ttu-id="ba026-142">**オプション** タブで、BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするためのオプションを指定し、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ba026-142">On the **Options** tab, specify the options for installing the BizTalk assembly to the global assembly cache (GAC), and then click **OK**.</span></span>  
  
## <a name="set-the-language-for-performing-operations"></a><span data-ttu-id="ba026-143">操作を実行するための言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="ba026-143">Set the Language for Performing Operations</span></span>  
 <span data-ttu-id="ba026-144">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の Oracle E-business Suite では、多言語サポート (MLS) 機能をサポートし、操作を実行中に言語を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ba026-144">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports the Multi-Language Support (MLS) feature of Oracle E-Business Suite, and allows you to specify a language while performing operations.</span></span> <span data-ttu-id="ba026-145">アダプターを公開、**言語**メッセージ コンテキスト プロパティの操作を実行するための言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba026-145">The adapter exposes the **Language** message context property to specify a language for performing operations.</span></span>  
  
 <span data-ttu-id="ba026-146">指定された値、**言語**メッセージ コンテキスト プロパティの値を上書きする、**言語**のプロパティのバインド、 **MlsSettings**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="ba026-146">The value specified for the **Language** message context property overrides the value of the **Language** binding property under the **MlsSettings** binding property.</span></span> <span data-ttu-id="ba026-147">詳細については、 **MlsSettings**プロパティ、バインドを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba026-147">For more information about the **MlsSettings** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
