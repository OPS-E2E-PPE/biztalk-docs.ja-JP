---
title: アダプター レジストリ ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a103dd40bfce3c4207d1d37eae0afd93fb868f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361258"
---
# <a name="adapter-registry-wizard"></a><span data-ttu-id="9e040-102">アダプター レジストリ ウィザード</span><span class="sxs-lookup"><span data-stu-id="9e040-102">Adapter Registry Wizard</span></span>
<span data-ttu-id="9e040-103">アダプター レジストリ ウィザードを使用して、構成して、カスタム アダプターを登録するために必要なレジストリ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e040-103">You use the Adapter Registry Wizard to create the registry files needed to configure and register a custom adapter.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="9e040-104">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="9e040-104">Location in SDK</span></span>  
 <span data-ttu-id="9e040-105">*\<Installation Path\>* \SDK\Utilities\AdapterRegistryWizard\\</span><span class="sxs-lookup"><span data-stu-id="9e040-105">*\<Installation Path\>* \SDK\Utilities\AdapterRegistryWizard\\</span></span>  

## <a name="to-run-this-utility"></a><span data-ttu-id="9e040-106">このユーティリティを実行するには</span><span class="sxs-lookup"><span data-stu-id="9e040-106">To Run This Utility</span></span>  
 <span data-ttu-id="9e040-107">AdapterRegistryWizard.exe 実行可能ファイルを実行して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="9e040-107">Start the wizard by running the AdapterRegistryWizard.exe executable.</span></span> <span data-ttu-id="9e040-108">次のページでプロンプトことについては、アダプターとサポートされるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9e040-108">The pages that follow prompt you for information about your adapter and the properties that it supports.</span></span> <span data-ttu-id="9e040-109">個別のアダプター レジストリ ウィザードのページは、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="9e040-109">The individual Adapter Registry Wizard pages are described in the sections that follow.</span></span>  

### <a name="generic-adapter-properties-page"></a><span data-ttu-id="9e040-110">ジェネリックのアダプターのプロパティ ページ</span><span class="sxs-lookup"><span data-stu-id="9e040-110">Generic Adapter Properties page</span></span>  
 <span data-ttu-id="9e040-111">汎用のアダプター プロパティ ページを使用すると、アダプターのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e040-111">Use the Generic Adapter Properties page to specify adapter properties.</span></span>  


|                              <span data-ttu-id="9e040-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e040-112">Use this</span></span>                              |                                                                                           <span data-ttu-id="9e040-113">目的</span><span class="sxs-lookup"><span data-stu-id="9e040-113">To do this</span></span>                                                                                           |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                     <span data-ttu-id="9e040-114">**トランスポート アダプターの種類**</span><span class="sxs-lookup"><span data-stu-id="9e040-114">**Transport adapter type**</span></span>                     |                                                                                   <span data-ttu-id="9e040-115">アダプターの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-115">Specify the adapter type.</span></span>                                                                                    |
|                       <span data-ttu-id="9e040-116">**プロパティの名前空間**</span><span class="sxs-lookup"><span data-stu-id="9e040-116">**Property namespace**</span></span>                       | <span data-ttu-id="9e040-117">アダプターの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-117">Specify the adapter namespace.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9e040-118">この名前空間のメッセージ コンテキストでは、アダプター固有のプロパティを格納します。</span><span class="sxs-lookup"><span data-stu-id="9e040-118">stores adapter-specific properties on the message context in this namespace.</span></span> |
| <span data-ttu-id="9e040-119">**アダプターはメッセージを受信し、BizTalk Server に送信します。**</span><span class="sxs-lookup"><span data-stu-id="9e040-119">**Adapter can receive messages and submit them to BizTalk Server**</span></span> |                                  <span data-ttu-id="9e040-120">アダプターでサポートされる通信パターンを特定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-120">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="9e040-121">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="9e040-121">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |
|         <span data-ttu-id="9e040-122">**アダプターは BizTalk Server からメッセージを送信することができます。**</span><span class="sxs-lookup"><span data-stu-id="9e040-122">**Adapter can send messages from BizTalk Server**</span></span>          |                                  <span data-ttu-id="9e040-123">アダプターでサポートされる通信パターンを特定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-123">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="9e040-124">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="9e040-124">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |

### <a name="inbound-part-page"></a><span data-ttu-id="9e040-125">Inbound Part ページ</span><span class="sxs-lookup"><span data-stu-id="9e040-125">Inbound Part page</span></span>  
 <span data-ttu-id="9e040-126">Inbound Part ページを使用すると、アダプターの受信の受信ロジックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e040-126">Use the Inbound Part page to specify inbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="9e040-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e040-127">Use this</span></span>|<span data-ttu-id="9e040-128">目的</span><span class="sxs-lookup"><span data-stu-id="9e040-128">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="9e040-129">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="9e040-129">**Browse**</span></span>|<span data-ttu-id="9e040-130">アダプターの受信の受信ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-130">Select the assembly that implements the inbound receiving logic for your adapter.</span></span> <span data-ttu-id="9e040-131">このアセンブリによって公開されるパブリック型の一覧は、ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e040-131">A list of the public types exposed by this assembly appear in the drop-down list.</span></span> <span data-ttu-id="9e040-132">ドロップダウン リストから、このアダプターの受信ロジックを実装する指定されたアセンブリ内の型を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-132">Select the type within the specified assembly that implements the inbound logic for this adapter from the drop-down list.</span></span>|  
|<span data-ttu-id="9e040-133">**アダプターは、要求-応答プロトコルをサポートしています**</span><span class="sxs-lookup"><span data-stu-id="9e040-133">**Adapter supports request-response protocol**</span></span>|<span data-ttu-id="9e040-134">アダプターの受信機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-134">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="9e040-135">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="9e040-135">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
|<span data-ttu-id="9e040-136">**アダプターは分離されています (別のプロセスでホストされる)**</span><span class="sxs-lookup"><span data-stu-id="9e040-136">**Adapter is isolated (that is hosted in a different process)**</span></span>|<span data-ttu-id="9e040-137">アダプターの受信機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-137">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="9e040-138">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="9e040-138">Used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="outbound-part-page"></a><span data-ttu-id="9e040-139">Outbound Part ページ</span><span class="sxs-lookup"><span data-stu-id="9e040-139">Outbound Part page</span></span>  
 <span data-ttu-id="9e040-140">[Outbound Part] ページを使用すると、アダプターの送信の受信ロジックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e040-140">Use the Outbound Part page to specify outbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="9e040-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e040-141">Use this</span></span>|<span data-ttu-id="9e040-142">目的</span><span class="sxs-lookup"><span data-stu-id="9e040-142">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="9e040-143">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="9e040-143">**Browse**</span></span>|<span data-ttu-id="9e040-144">アダプターの送信の受信ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-144">Select the assembly that implements the outbound receiving logic for your adapter.</span></span> <span data-ttu-id="9e040-145">ドロップダウン リストで、このアセンブリによって公開されるパブリック型の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e040-145">A list of the public types exposed by this assembly appears in the drop-down list .</span></span> <span data-ttu-id="9e040-146">ドロップダウン リストから、このアダプターの送信ロジックを実装する指定されたアセンブリの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-146">Select the type for the specified assembly that implements the outbound logic for this adapter from the drop-down list.</span></span> <span data-ttu-id="9e040-147">このアダプターによって使用されるプロトコルを識別するために使用するエイリアスのコンマ区切りの一覧を入力することも必要があります (たとえば、送信://)。</span><span class="sxs-lookup"><span data-stu-id="9e040-147">You must also enter a comma-separated list of aliases used to identify the protocol used by this adapter (for example, submit://).</span></span>|  
|<span data-ttu-id="9e040-148">**アダプターが送信請求-応答プロトコルをサポートしています**</span><span class="sxs-lookup"><span data-stu-id="9e040-148">**Adapter supports solicit-response protocol**</span></span>|<span data-ttu-id="9e040-149">アダプターの送信機能を特定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-149">Identify the transmitting capabilities of your adapter.</span></span> <span data-ttu-id="9e040-150">これらの値は、アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e040-150">These values are used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="adapter-management-page"></a><span data-ttu-id="9e040-151">Adapter Management ページ</span><span class="sxs-lookup"><span data-stu-id="9e040-151">Adapter Management page</span></span>  
 <span data-ttu-id="9e040-152">Adapter Management ページを使用すると、アダプターのデザイン時管理ロジックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e040-152">Use the Adapter Management page to specify design-time management logic for your adapter.</span></span>  

|<span data-ttu-id="9e040-153">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e040-153">Use this</span></span>|<span data-ttu-id="9e040-154">目的</span><span class="sxs-lookup"><span data-stu-id="9e040-154">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="9e040-155">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="9e040-155">**Browse**</span></span>|<span data-ttu-id="9e040-156">アダプターのデザイン時アダプター管理ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-156">Select the assembly that implements the design-time adapter management logic for your adapter.</span></span> <span data-ttu-id="9e040-157">ドロップダウン リストで、このアセンブリによって公開されるパブリック型の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e040-157">A list of the public types exposed by this assembly appears in the drop-down list.</span></span> <span data-ttu-id="9e040-158">ドロップダウン リストから、このアダプターのアダプター管理ロジックを実装する指定されたアセンブリの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-158">Select the type for the specified assembly that implements the adapter management logic for this adapter from the drop-down list.</span></span>|  

### <a name="output-file-name"></a><span data-ttu-id="9e040-159">出力ファイル名</span><span class="sxs-lookup"><span data-stu-id="9e040-159">Output File name</span></span>  
 <span data-ttu-id="9e040-160">出力ファイル名 ページを使用すると、出力ファイルの名前と場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e040-160">Use the Output file name page to specify an output file name and location.</span></span>  

|<span data-ttu-id="9e040-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e040-161">Use this</span></span>|<span data-ttu-id="9e040-162">目的</span><span class="sxs-lookup"><span data-stu-id="9e040-162">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="9e040-163">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="9e040-163">**Browse**</span></span>|<span data-ttu-id="9e040-164">出力ファイルの名前と場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e040-164">Choose an output file name and location.</span></span> <span data-ttu-id="9e040-165">アダプターのレジストリは、このファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9e040-165">The adapter registry is written to this file.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="9e040-166">コメント</span><span class="sxs-lookup"><span data-stu-id="9e040-166">Remarks</span></span>  
 <span data-ttu-id="9e040-167">アダプター レジストリ ウィザード ユーティリティでは、既定値では、エンタープライズ シングル サインオン (SSO) 構成ストア プロパティは設定します。</span><span class="sxs-lookup"><span data-stu-id="9e040-167">The Adapter Registry Wizard utility populates the Enterprise Single Sign-On (SSO) configuration store properties with default values.</span></span> <span data-ttu-id="9e040-168">アダプターがアダプターのプロパティのハンドラー、および場所のアダプター フレームワークによって提供される標準のプロパティ ページを使用しない場合は、これらの値を変更するには、手動でレジストリ ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e040-168">If your adapter does not use the standard property pages provided by the Adapter Framework for handler and location adapter properties, you must edit the registry file manually to modify these values.</span></span> <span data-ttu-id="9e040-169">これらの設定の詳細については、トピックの「SSO 構成ストアのアダプター プロパティの登録」を参照してください。[アダプターの登録](../core/registering-an-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9e040-169">For more information about these settings, see "Registration of adapter properties for SSO configuration store" in the topic [Registering an Adapter](../core/registering-an-adapter.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="9e040-170">参照</span><span class="sxs-lookup"><span data-stu-id="9e040-170">See Also</span></span>  
 <span data-ttu-id="9e040-171">[SDK のユーティリティ](../core/utilities-in-the-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="9e040-171">[Utilities in the SDK](../core/utilities-in-the-sdk.md) </span></span>  
 [<span data-ttu-id="9e040-172">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="9e040-172">Registering an Adapter</span></span>](../core/registering-an-adapter.md)