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
ms.openlocfilehash: 13842e4edda428f53cc4d11c2cbe7c06407fe2e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004803"
---
# <a name="adapter-registry-wizard"></a><span data-ttu-id="05649-102">アダプター レジストリ ウィザード</span><span class="sxs-lookup"><span data-stu-id="05649-102">Adapter Registry Wizard</span></span>
<span data-ttu-id="05649-103">アダプター レジストリ ウィザードを使用すると、カスタム アダプターの構成と登録に必要なレジストリ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="05649-103">You use the Adapter Registry Wizard to create the registry files needed to configure and register a custom adapter.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="05649-104">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="05649-104">Location in SDK</span></span>  
 <span data-ttu-id="05649-105">*\<インストール パス\>* \SDK\Utilities\AdapterRegistryWizard\\</span><span class="sxs-lookup"><span data-stu-id="05649-105">*\<Installation Path\>* \SDK\Utilities\AdapterRegistryWizard\\</span></span>  

## <a name="to-run-this-utility"></a><span data-ttu-id="05649-106">このユーティリティを実行するには</span><span class="sxs-lookup"><span data-stu-id="05649-106">To Run This Utility</span></span>  
 <span data-ttu-id="05649-107">AdapterRegistryWizard.exe 実行可能ファイルを実行して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="05649-107">Start the wizard by running the AdapterRegistryWizard.exe executable.</span></span> <span data-ttu-id="05649-108">次のページで、アダプターとアダプターでサポートされるプロパティについての情報の入力を要求されます。</span><span class="sxs-lookup"><span data-stu-id="05649-108">The pages that follow prompt you for information about your adapter and the properties that it supports.</span></span> <span data-ttu-id="05649-109">個別のアダプター レジストリ ウィザードのページについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="05649-109">The individual Adapter Registry Wizard pages are described in the sections that follow.</span></span>  

### <a name="generic-adapter-properties-page"></a><span data-ttu-id="05649-110">アダプターのプロパティ ぺージ</span><span class="sxs-lookup"><span data-stu-id="05649-110">Generic Adapter Properties page</span></span>  
 <span data-ttu-id="05649-111">アダプターのプロパティ ページを使用して、アダプターのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-111">Use the Generic Adapter Properties page to specify adapter properties.</span></span>  


|                              <span data-ttu-id="05649-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="05649-112">Use this</span></span>                              |                                                                                           <span data-ttu-id="05649-113">目的</span><span class="sxs-lookup"><span data-stu-id="05649-113">To do this</span></span>                                                                                           |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                     <span data-ttu-id="05649-114">**トランスポート アダプターの種類**</span><span class="sxs-lookup"><span data-stu-id="05649-114">**Transport adapter type**</span></span>                     |                                                                                   <span data-ttu-id="05649-115">アダプターの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-115">Specify the adapter type.</span></span>                                                                                    |
|                       <span data-ttu-id="05649-116">**プロパティの名前空間**</span><span class="sxs-lookup"><span data-stu-id="05649-116">**Property namespace**</span></span>                       | <span data-ttu-id="05649-117">アダプターの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-117">Specify the adapter namespace.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="05649-118"> この名前空間のメッセージ コンテキストでは、アダプター固有のプロパティを格納します。</span><span class="sxs-lookup"><span data-stu-id="05649-118"> stores adapter-specific properties on the message context in this namespace.</span></span> |
| <span data-ttu-id="05649-119">**アダプターはメッセージを受信し、BizTalk Server に送信します。**</span><span class="sxs-lookup"><span data-stu-id="05649-119">**Adapter can receive messages and submit them to BizTalk Server**</span></span> |                                  <span data-ttu-id="05649-120">アダプターでサポートされる通信方式を特定します。</span><span class="sxs-lookup"><span data-stu-id="05649-120">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="05649-121">アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="05649-121">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |
|         <span data-ttu-id="05649-122">**アダプターは BizTalk Server からメッセージを送信することができます。**</span><span class="sxs-lookup"><span data-stu-id="05649-122">**Adapter can send messages from BizTalk Server**</span></span>          |                                  <span data-ttu-id="05649-123">アダプターでサポートされる通信方式を特定します。</span><span class="sxs-lookup"><span data-stu-id="05649-123">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="05649-124">アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="05649-124">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |

### <a name="inbound-part-page"></a><span data-ttu-id="05649-125">[Inbound Part] ページ</span><span class="sxs-lookup"><span data-stu-id="05649-125">Inbound Part page</span></span>  
 <span data-ttu-id="05649-126">[Inbound Part] ページを使用して、アダプターの受信の受信ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-126">Use the Inbound Part page to specify inbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="05649-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="05649-127">Use this</span></span>|<span data-ttu-id="05649-128">目的</span><span class="sxs-lookup"><span data-stu-id="05649-128">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="05649-129">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="05649-129">**Browse**</span></span>|<span data-ttu-id="05649-130">アダプターの受信の受信ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-130">Select the assembly that implements the inbound receiving logic for your adapter.</span></span> <span data-ttu-id="05649-131">このアセンブリによって公開されるパブリック型の一覧は、ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="05649-131">A list of the public types exposed by this assembly appear in the drop-down list.</span></span> <span data-ttu-id="05649-132">ドロップダウン リストから、このアダプターの受信ロジックを実装する指定されたアセンブリ内の型を選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-132">Select the type within the specified assembly that implements the inbound logic for this adapter from the drop-down list.</span></span>|  
|<span data-ttu-id="05649-133">**アダプターは、要求-応答プロトコルをサポートしています**</span><span class="sxs-lookup"><span data-stu-id="05649-133">**Adapter supports request-response protocol**</span></span>|<span data-ttu-id="05649-134">アダプターの受信機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-134">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="05649-135">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="05649-135">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
|<span data-ttu-id="05649-136">**アダプターは分離されています (別のプロセスでホストされる)**</span><span class="sxs-lookup"><span data-stu-id="05649-136">**Adapter is isolated (that is hosted in a different process)**</span></span>|<span data-ttu-id="05649-137">アダプターの受信機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-137">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="05649-138">アダプターの制約のレジストリ エントリの計算に使用します。</span><span class="sxs-lookup"><span data-stu-id="05649-138">Used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="outbound-part-page"></a><span data-ttu-id="05649-139">[Outbound Part] ページ</span><span class="sxs-lookup"><span data-stu-id="05649-139">Outbound Part page</span></span>  
 <span data-ttu-id="05649-140">[Outbound Part] ページを使用して、アダプターの送信の受信ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-140">Use the Outbound Part page to specify outbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="05649-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="05649-141">Use this</span></span>|<span data-ttu-id="05649-142">目的</span><span class="sxs-lookup"><span data-stu-id="05649-142">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="05649-143">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="05649-143">**Browse**</span></span>|<span data-ttu-id="05649-144">アダプターの送信の受信ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-144">Select the assembly that implements the outbound receiving logic for your adapter.</span></span> <span data-ttu-id="05649-145">ドロップダウン リストで、このアセンブリによって公開されるパブリック型の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05649-145">A list of the public types exposed by this assembly appears in the drop-down list .</span></span> <span data-ttu-id="05649-146">ドロップダウン リストから、このアダプターの送信ロジックを実装する指定されたアセンブリの型を選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-146">Select the type for the specified assembly that implements the outbound logic for this adapter from the drop-down list.</span></span> <span data-ttu-id="05649-147">このアダプターで使用されるプロトコル (submit:// など) を識別するために使用するエイリアスの一覧をコンマで区切って入力する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="05649-147">You must also enter a comma-separated list of aliases used to identify the protocol used by this adapter (for example, submit://).</span></span>|  
|<span data-ttu-id="05649-148">**アダプターが送信請求-応答プロトコルをサポートしています**</span><span class="sxs-lookup"><span data-stu-id="05649-148">**Adapter supports solicit-response protocol**</span></span>|<span data-ttu-id="05649-149">アダプターの送信機能を特定します。</span><span class="sxs-lookup"><span data-stu-id="05649-149">Identify the transmitting capabilities of your adapter.</span></span> <span data-ttu-id="05649-150">この値は、アダプターの制約のレジストリ エントリの計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="05649-150">These values are used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="adapter-management-page"></a><span data-ttu-id="05649-151">Adapter Management ページ</span><span class="sxs-lookup"><span data-stu-id="05649-151">Adapter Management page</span></span>  
 <span data-ttu-id="05649-152">Adapter Management ページを使用して、アダプターのデザイン時管理ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-152">Use the Adapter Management page to specify design-time management logic for your adapter.</span></span>  

|<span data-ttu-id="05649-153">プロパティ</span><span class="sxs-lookup"><span data-stu-id="05649-153">Use this</span></span>|<span data-ttu-id="05649-154">目的</span><span class="sxs-lookup"><span data-stu-id="05649-154">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="05649-155">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="05649-155">**Browse**</span></span>|<span data-ttu-id="05649-156">アダプターのデザイン時アダプター管理ロジックを実装するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-156">Select the assembly that implements the design-time adapter management logic for your adapter.</span></span> <span data-ttu-id="05649-157">このアセンブリで公開されるパブリック型の一覧が、ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="05649-157">A list of the public types exposed by this assembly appears in the drop-down list.</span></span> <span data-ttu-id="05649-158">ドロップダウン リストから、このアダプターのアダプター管理ロジックを実装する指定されたアセンブリの型を選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-158">Select the type for the specified assembly that implements the adapter management logic for this adapter from the drop-down list.</span></span>|  

### <a name="output-file-name"></a><span data-ttu-id="05649-159">出力ファイル名</span><span class="sxs-lookup"><span data-stu-id="05649-159">Output File name</span></span>  
 <span data-ttu-id="05649-160">出力ファイル名ページを使用して、出力ファイルの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="05649-160">Use the Output file name page to specify an output file name and location.</span></span>  

|<span data-ttu-id="05649-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="05649-161">Use this</span></span>|<span data-ttu-id="05649-162">目的</span><span class="sxs-lookup"><span data-stu-id="05649-162">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="05649-163">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="05649-163">**Browse**</span></span>|<span data-ttu-id="05649-164">出力ファイルの名前と場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="05649-164">Choose an output file name and location.</span></span> <span data-ttu-id="05649-165">アダプターのレジストリは、このファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="05649-165">The adapter registry is written to this file.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="05649-166">コメント</span><span class="sxs-lookup"><span data-stu-id="05649-166">Remarks</span></span>  
 <span data-ttu-id="05649-167">アダプター レジストリ ウィザード ユーティリティでは、エンタープライズ シングル サインオン (SSO) 構成ストア プロパティは既定値で設定されます。</span><span class="sxs-lookup"><span data-stu-id="05649-167">The Adapter Registry Wizard utility populates the Enterprise Single Sign-On (SSO) configuration store properties with default values.</span></span> <span data-ttu-id="05649-168">ハンドラーと配置アダプターのプロパティ用としてアダプター フレームワークで提供される標準のプロパティ ページをアダプターで使用しない場合、これらの値を変更するにはレジストリ ファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05649-168">If your adapter does not use the standard property pages provided by the Adapter Framework for handler and location adapter properties, you must edit the registry file manually to modify these values.</span></span> <span data-ttu-id="05649-169">これらの設定の詳細については、トピックの「SSO 構成ストアのアダプター プロパティの登録」を参照してください。[アダプターの登録](../core/registering-an-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="05649-169">For more information about these settings, see "Registration of adapter properties for SSO configuration store" in the topic [Registering an Adapter](../core/registering-an-adapter.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="05649-170">参照</span><span class="sxs-lookup"><span data-stu-id="05649-170">See Also</span></span>  
 <span data-ttu-id="05649-171">[SDK のユーティリティ](../core/utilities-in-the-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="05649-171">[Utilities in the SDK](../core/utilities-in-the-sdk.md) </span></span>  
 [<span data-ttu-id="05649-172">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="05649-172">Registering an Adapter</span></span>](../core/registering-an-adapter.md)