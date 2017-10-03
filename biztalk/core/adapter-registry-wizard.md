---
title: "アダプター レジストリ ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f07ef6adc96a4f5819cd5438b4a5d24ce6fc0770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-registry-wizard"></a><span data-ttu-id="6525a-102">アダプター レジストリ ウィザード</span><span class="sxs-lookup"><span data-stu-id="6525a-102">Adapter Registry Wizard</span></span>
<span data-ttu-id="6525a-103">アダプター レジストリ ウィザードを使用すると、カスタム アダプターの構成と登録に必要なレジストリ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6525a-103">You use the Adapter Registry Wizard to create the registry files needed to configure and register a custom adapter.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="6525a-104">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="6525a-104">Location in SDK</span></span>  
 <span data-ttu-id="6525a-105">*\<インストール パス >*\SDK\Utilities\AdapterRegistryWizard\\</span><span class="sxs-lookup"><span data-stu-id="6525a-105">*\<Installation Path>*\SDK\Utilities\AdapterRegistryWizard\\</span></span>  
  
## <a name="to-run-this-utility"></a><span data-ttu-id="6525a-106">このユーティリティを実行するには</span><span class="sxs-lookup"><span data-stu-id="6525a-106">To Run This Utility</span></span>  
 <span data-ttu-id="6525a-107">AdapterRegistryWizard.exe 実行可能ファイルを実行して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="6525a-107">Start the wizard by running the AdapterRegistryWizard.exe executable.</span></span> <span data-ttu-id="6525a-108">次のページで、アダプターとアダプターでサポートされるプロパティについての情報の入力を要求されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-108">The pages that follow prompt you for information about your adapter and the properties that it supports.</span></span> <span data-ttu-id="6525a-109">個別のアダプター レジストリ ウィザードのページについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="6525a-109">The individual Adapter Registry Wizard pages are described in the sections that follow.</span></span>  
  
### <a name="generic-adapter-properties-page"></a><span data-ttu-id="6525a-110">アダプターのプロパティ ぺージ</span><span class="sxs-lookup"><span data-stu-id="6525a-110">Generic Adapter Properties page</span></span>  
 <span data-ttu-id="6525a-111">アダプターのプロパティ ページを使用して、アダプターのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-111">Use the Generic Adapter Properties page to specify adapter properties.</span></span>  
  
|<span data-ttu-id="6525a-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6525a-112">Use this</span></span>|<span data-ttu-id="6525a-113">目的</span><span class="sxs-lookup"><span data-stu-id="6525a-113">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6525a-114">**トランスポート アダプターの種類**</span><span class="sxs-lookup"><span data-stu-id="6525a-114">**Transport adapter type**</span></span>|<span data-ttu-id="6525a-115">アダプターの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-115">Specify the adapter type.</span></span>|  
|<span data-ttu-id="6525a-116">**プロパティの名前空間**</span><span class="sxs-lookup"><span data-stu-id="6525a-116">**Property namespace**</span></span>|<span data-ttu-id="6525a-117">アダプタの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-117">Specify the adapter namespace.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6525a-118">この名前空間のメッセージ コンテキストでは、アダプターに固有のプロパティを格納します。</span><span class="sxs-lookup"><span data-stu-id="6525a-118"> stores adapter-specific properties on the message context in this namespace.</span></span>|  
|<span data-ttu-id="6525a-119">**アダプターがメッセージを受信して、BizTalk Server に送信します。**</span><span class="sxs-lookup"><span data-stu-id="6525a-119">**Adapter can receive messages and submit them to BizTalk Server**</span></span>|<span data-ttu-id="6525a-120">アダプターでサポートされる通信方式を特定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-120">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="6525a-121">アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-121">Used to calculate the Constraints registry entry for the adapter.</span></span>|  
|<span data-ttu-id="6525a-122">**アダプターは BizTalk Server からメッセージを送信することができます。**</span><span class="sxs-lookup"><span data-stu-id="6525a-122">**Adapter can send messages from BizTalk Server**</span></span>|<span data-ttu-id="6525a-123">アダプターでサポートされる通信方式を特定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-123">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="6525a-124">アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-124">Used to calculate the Constraints registry entry for the adapter.</span></span>|  
  
### <a name="inbound-part-page"></a><span data-ttu-id="6525a-125">[Inbound Part] ページ</span><span class="sxs-lookup"><span data-stu-id="6525a-125">Inbound Part page</span></span>  
 <span data-ttu-id="6525a-126">[Inbound Part] ページを使用して、アダプターの受信の受信ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-126">Use the Inbound Part page to specify inbound receiving logic for your adapter.</span></span>  
  
|<span data-ttu-id="6525a-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6525a-127">Use this</span></span>|<span data-ttu-id="6525a-128">目的</span><span class="sxs-lookup"><span data-stu-id="6525a-128">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6525a-129">**参照**</span><span class="sxs-lookup"><span data-stu-id="6525a-129">**Browse**</span></span>|<span data-ttu-id="6525a-130">アダプターの受信の受信ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-130">Select the assembly that implements the inbound receiving logic for your adapter.</span></span> <span data-ttu-id="6525a-131">このアセンブリによって公開されているパブリック型の一覧は、ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-131">A list of the public types exposed by this assembly appear in the drop-down list.</span></span> <span data-ttu-id="6525a-132">ドロップダウン リストから、このアダプターの受信ロジックを実装する指定されたアセンブリ内の型を選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-132">Select the type within the specified assembly that implements the inbound logic for this adapter from the drop-down list.</span></span>|  
|<span data-ttu-id="6525a-133">**アダプターは、要求-応答プロトコルをサポートしています**</span><span class="sxs-lookup"><span data-stu-id="6525a-133">**Adapter supports request-response protocol**</span></span>|<span data-ttu-id="6525a-134">アダプターの受信機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-134">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="6525a-135">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="6525a-135">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
|<span data-ttu-id="6525a-136">**アダプターは分離されて (別のプロセスでホストされる)**</span><span class="sxs-lookup"><span data-stu-id="6525a-136">**Adapter is isolated (that is hosted in a different process)**</span></span>|<span data-ttu-id="6525a-137">アダプターの受信機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-137">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="6525a-138">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="6525a-138">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
  
### <a name="outbound-part-page"></a><span data-ttu-id="6525a-139">[Outbound Part] ページ</span><span class="sxs-lookup"><span data-stu-id="6525a-139">Outbound Part page</span></span>  
 <span data-ttu-id="6525a-140">[Outbound Part] ページを使用して、アダプターの送信の受信ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-140">Use the Outbound Part page to specify outbound receiving logic for your adapter.</span></span>  
  
|<span data-ttu-id="6525a-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6525a-141">Use this</span></span>|<span data-ttu-id="6525a-142">目的</span><span class="sxs-lookup"><span data-stu-id="6525a-142">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6525a-143">**参照**</span><span class="sxs-lookup"><span data-stu-id="6525a-143">**Browse**</span></span>|<span data-ttu-id="6525a-144">アダプターの送信の受信ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-144">Select the assembly that implements the outbound receiving logic for your adapter.</span></span> <span data-ttu-id="6525a-145">このアセンブリによって公開されているパブリック型の一覧は、ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-145">A list of the public types exposed by this assembly appears in the drop-down list .</span></span> <span data-ttu-id="6525a-146">ドロップダウン リストから、このアダプターの送信ロジックを実装する指定されたアセンブリの型を選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-146">Select the type for the specified assembly that implements the outbound logic for this adapter from the drop-down list.</span></span> <span data-ttu-id="6525a-147">このアダプターで使用されるプロトコル (submit:// など) を識別するために使用するエイリアスの一覧をコンマで区切って入力する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6525a-147">You must also enter a comma-separated list of aliases used to identify the protocol used by this adapter (for example, submit://).</span></span>|  
|<span data-ttu-id="6525a-148">**アダプターは、送信請求-応答プロトコルをサポートしています**</span><span class="sxs-lookup"><span data-stu-id="6525a-148">**Adapter supports solicit-response protocol**</span></span>|<span data-ttu-id="6525a-149">アダプターの送信機能を特定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-149">Identify the transmitting capabilities of your adapter.</span></span> <span data-ttu-id="6525a-150">この値は、アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-150">These values are used to calculate the Constraints registry entry for your adapter.</span></span>|  
  
### <a name="adapter-management-page"></a><span data-ttu-id="6525a-151">Adapter Management ページ</span><span class="sxs-lookup"><span data-stu-id="6525a-151">Adapter Management page</span></span>  
 <span data-ttu-id="6525a-152">Adapter Management ページを使用して、アダプターのデザイン時管理ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-152">Use the Adapter Management page to specify design-time management logic for your adapter.</span></span>  
  
|<span data-ttu-id="6525a-153">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6525a-153">Use this</span></span>|<span data-ttu-id="6525a-154">目的</span><span class="sxs-lookup"><span data-stu-id="6525a-154">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6525a-155">**参照**</span><span class="sxs-lookup"><span data-stu-id="6525a-155">**Browse**</span></span>|<span data-ttu-id="6525a-156">アダプターのデザイン時アダプター管理ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-156">Select the assembly that implements the design-time adapter management logic for your adapter.</span></span> <span data-ttu-id="6525a-157">このアセンブリで公開されるパブリック型の一覧が、ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-157">A list of the public types exposed by this assembly appears in the drop-down list.</span></span> <span data-ttu-id="6525a-158">ドロップダウン リストから、このアダプターのアダプター管理ロジックを実装する指定されたアセンブリの型を選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-158">Select the type for the specified assembly that implements the adapter management logic for this adapter from the drop-down list.</span></span>|  
  
### <a name="output-file-name"></a><span data-ttu-id="6525a-159">出力ファイル名</span><span class="sxs-lookup"><span data-stu-id="6525a-159">Output File name</span></span>  
 <span data-ttu-id="6525a-160">出力ファイル名ページを使用して、出力ファイルの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6525a-160">Use the Output file name page to specify an output file name and location.</span></span>  
  
|<span data-ttu-id="6525a-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6525a-161">Use this</span></span>|<span data-ttu-id="6525a-162">目的</span><span class="sxs-lookup"><span data-stu-id="6525a-162">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6525a-163">**参照**</span><span class="sxs-lookup"><span data-stu-id="6525a-163">**Browse**</span></span>|<span data-ttu-id="6525a-164">出力ファイルの名前と場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="6525a-164">Choose an output file name and location.</span></span> <span data-ttu-id="6525a-165">アダプターのレジストリは、このファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="6525a-165">The adapter registry is written to this file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6525a-166">解説</span><span class="sxs-lookup"><span data-stu-id="6525a-166">Remarks</span></span>  
 <span data-ttu-id="6525a-167">アダプター レジストリ ウィザード ユーティリティでは、エンタープライズ シングル サインオン (SSO) 構成ストア プロパティは既定値で設定されます。</span><span class="sxs-lookup"><span data-stu-id="6525a-167">The Adapter Registry Wizard utility populates the Enterprise Single Sign-On (SSO) configuration store properties with default values.</span></span> <span data-ttu-id="6525a-168">ハンドラーと配置アダプターのプロパティ用としてアダプター フレームワークで提供される標準のプロパティ ページをアダプターで使用しない場合、これらの値を変更するにはレジストリ ファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6525a-168">If your adapter does not use the standard property pages provided by the Adapter Framework for handler and location adapter properties, you must edit the registry file manually to modify these values.</span></span> <span data-ttu-id="6525a-169">これらの設定の詳細についてを参照してください「SSO 構成ストアのアダプターのプロパティの登録」のトピックで[アダプターの登録](../core/registering-an-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="6525a-169">For more information about these settings, see "Registration of adapter properties for SSO configuration store" in the topic [Registering an Adapter](../core/registering-an-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6525a-170">参照</span><span class="sxs-lookup"><span data-stu-id="6525a-170">See Also</span></span>  
 <span data-ttu-id="6525a-171">[SDK のユーティリティ](../core/utilities-in-the-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="6525a-171">[Utilities in the SDK](../core/utilities-in-the-sdk.md) </span></span>  
 [<span data-ttu-id="6525a-172">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="6525a-172">Registering an Adapter</span></span>](../core/registering-an-adapter.md)