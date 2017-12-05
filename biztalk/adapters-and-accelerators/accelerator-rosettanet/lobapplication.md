---
title: "LOBApplication |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af11e69c90c9d211e36e706710c1d1de44a72399
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lobapplication"></a><span data-ttu-id="73641-102">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="73641-102">LOBApplication</span></span>
<span data-ttu-id="73641-103">実際の基幹業務 (LOB) デスクトップ プログラムをシミュレートして、アクション メッセージまたは応答メッセージを取引先に送信するには、LOBApplication ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="73641-103">You use the LOBApplication utility to submit an action or response message to a trading partner, simulating an actual line-of-business (LOB) desktop program.</span></span>  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="73641-104">®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]にサンプル メッセージを提供、 \<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>RosettaNet\SDK\LOBApplication\ のアクセラレータSampleInstances フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="73641-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides sample messages in the \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="73641-105">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="73641-105">Location in SDK</span></span>  
 <span data-ttu-id="73641-106">\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication</span><span class="sxs-lookup"><span data-stu-id="73641-106">\<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication</span></span>  
  
## <a name="running-lobapplication"></a><span data-ttu-id="73641-107">LOBApplication の実行</span><span class="sxs-lookup"><span data-stu-id="73641-107">Running LOBApplication</span></span>  
  
#### <a name="to-run-lobapplication"></a><span data-ttu-id="73641-108">LOBApplication を実行するには</span><span class="sxs-lookup"><span data-stu-id="73641-108">To run LOBApplication</span></span>  
  
1.  <span data-ttu-id="73641-109">Windows エクスプローラで、移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\です。</span><span class="sxs-lookup"><span data-stu-id="73641-109">In Windows Explorer, move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
2.  <span data-ttu-id="73641-110">ダブルクリックして**LOBApplication.exe**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="73641-110">Double-click **LOBApplication.exe**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="73641-111">ユーティリティの実行に必要な情報を入力するためのページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73641-111">The pages that follow prompt you for the information that is required to run the utility.</span></span>  
  
## <a name="syntax-for-lobapplication"></a><span data-ttu-id="73641-112">LOBApplication の構文</span><span class="sxs-lookup"><span data-stu-id="73641-112">Syntax for LOBApplication</span></span>  
 <span data-ttu-id="73641-113">使用して、 **LOB Application**ページをホーム組織とパートナーの名前、プロセス PIP (Partner Interface) プロパティ、および LOBApplication ユーティリティによって送信されたメッセージのメッセージのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="73641-113">Use the **LOB Application Proxy** page to specify home and partner names, Partner Interface Process (PIP) properties, and message properties for the message sent by the LOBApplication utility.</span></span>  
  
 <span data-ttu-id="73641-114">次の表に、上の各フィールドを使用する方法、 **LOB Application**ページ。</span><span class="sxs-lookup"><span data-stu-id="73641-114">The following table describes how to use each field on the **LOB Application Proxy** page.</span></span>  
  
|<span data-ttu-id="73641-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="73641-115">Use this</span></span>|<span data-ttu-id="73641-116">目的</span><span class="sxs-lookup"><span data-stu-id="73641-116">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="73641-117">**Home Profile Name**</span><span class="sxs-lookup"><span data-stu-id="73641-117">**Home Profile Name**</span></span>|<span data-ttu-id="73641-118">ホーム組織 (送信元パーティ) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="73641-118">Type the name of the home organization (source party).</span></span>|  
|<span data-ttu-id="73641-119">**取引先名**</span><span class="sxs-lookup"><span data-stu-id="73641-119">**Trading Partner Name**</span></span>|<span data-ttu-id="73641-120">取引先 (送信先パーティ) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="73641-120">Type the name of the trading partner (destination party).</span></span>|  
|<span data-ttu-id="73641-121">**PIP の名前**</span><span class="sxs-lookup"><span data-stu-id="73641-121">**PIP Name**</span></span>|<span data-ttu-id="73641-122">PIP、たとえば、型の表示コードを入力**3 a 2**です。</span><span class="sxs-lookup"><span data-stu-id="73641-122">Type the display code of the PIP, for example, type **3A2**.</span></span> <span data-ttu-id="73641-123">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="73641-123">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="73641-124">**[PIP Version]**</span><span class="sxs-lookup"><span data-stu-id="73641-124">**PIP Version**</span></span>|<span data-ttu-id="73641-125">PIP、たとえば、型のバージョンを入力**V02.00**です。</span><span class="sxs-lookup"><span data-stu-id="73641-125">Type the version of the PIP, for example, type **V02.00**.</span></span> <span data-ttu-id="73641-126">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="73641-126">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="73641-127">**PIP Instance ID** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="73641-127">**PIP Instance ID** (optional)</span></span>|<span data-ttu-id="73641-128">たとえば、入力、PIP の英数字のインスタンス ID を入力**STD_3A2_V02.02**です。</span><span class="sxs-lookup"><span data-stu-id="73641-128">Type an alphanumeric instance ID for the PIP, for example, type **STD_3A2_V02.02**.</span></span> <span data-ttu-id="73641-129">特殊文字は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="73641-129">Avoid special characters.</span></span> <span data-ttu-id="73641-130">この ID は取引先および PIP コードごとに固有でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="73641-130">The ID should be unique per partner and per PIP code.</span></span> <span data-ttu-id="73641-131">アクション メッセージとしてマークされたメッセージのインスタンス ID が空白の場合、LOBApplication ユーティリティでは、自動的に生成された HUID 値が PIP インスタンス ID として使用されます。</span><span class="sxs-lookup"><span data-stu-id="73641-131">For messages that are marked as action messages, if the Instance ID is empty, the LOBApplication utility uses a generated HUID value for the PIP Instance ID.</span></span> <span data-ttu-id="73641-132">**注:**を選択すると**応答**で、**メッセージ カテゴリ**、PIP インスタンス ID は、このフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73641-132">**Note:**  When you select **Response** in the **Message Category**, you must type the PIP Instance ID in this field.</span></span>|  
|<span data-ttu-id="73641-133">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="73641-133">**File Name**</span></span>|<span data-ttu-id="73641-134">省略記号 ([...]) ボタンをクリックし、PIP インスタンス ファイルが保存されているフォルダーに移動して、PIP インスタンス ファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="73641-134">Click the ellipsis button (...), go to the folder that contains the PIP instance file, and then click the PIP instance file.</span></span>|  
|<span data-ttu-id="73641-135">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="73641-135">**Message Category**</span></span>|<span data-ttu-id="73641-136">メッセージの種類の選択 (**アクション**または**応答**)。</span><span class="sxs-lookup"><span data-stu-id="73641-136">Select the type of message (**Action** or **Response**).</span></span>|  
|<span data-ttu-id="73641-137">**[Attachments]**</span><span class="sxs-lookup"><span data-stu-id="73641-137">**Attachments**</span></span>|<span data-ttu-id="73641-138">をクリックして**追加**添付ファイルを含むフォルダーに移動し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="73641-138">Click **Add**, move to the folder that contains the attachment file, and then click **Open**.</span></span>|  
|<span data-ttu-id="73641-139">**メッセージを送信します。**</span><span class="sxs-lookup"><span data-stu-id="73641-139">**Submit Message**</span></span>|<span data-ttu-id="73641-140">クリックしてメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="73641-140">Click to send the message.</span></span>|  
|<span data-ttu-id="73641-141">**[状態]**</span><span class="sxs-lookup"><span data-stu-id="73641-141">**Status**</span></span>|<span data-ttu-id="73641-142">このフィールドでは、アクションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="73641-142">Read the status of the action in this field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73641-143">解説</span><span class="sxs-lookup"><span data-stu-id="73641-143">Remarks</span></span>  
 <span data-ttu-id="73641-144">LOBApplication ユーティリティは、指定されたプロパティに基づいてメッセージを作成し、それを取引先に送信します。</span><span class="sxs-lookup"><span data-stu-id="73641-144">The LOBApplication utility creates a message with the properties specified, and sends it to the trading partner.</span></span> <span data-ttu-id="73641-145">このユーティリティは、メッセージの Service Content データを BTARNDATA データベースの MessageFromLOB テーブルに書き込み、</span><span class="sxs-lookup"><span data-stu-id="73641-145">This utility writes the service content data in the message to the BTARNDATA database, in the MessageFromLOB table.</span></span> <span data-ttu-id="73641-146">アクション メッセージの送信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="73641-146">This utility simulates sending an action message.</span></span>  
  
 <span data-ttu-id="73641-147">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK の LOBApplication フォルダー内の SampleInstances フォルダーに含まれているサンプル メッセージは、ホーム組織の場合は 123456789、取引先組織の場合は 987654321 という、グローバル ビジネス識別子 (GBI) を持つようにあらかじめ設定されています。</span><span class="sxs-lookup"><span data-stu-id="73641-147">The sample messages in the SampleInstances folder under the LOBApplication folder in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK are preconfigured to assume the following Global Business Identifiers (GBIs): 123456789 for the home organization and 987654321 for the partner organization.</span></span> <span data-ttu-id="73641-148">これ以外の GBI を使用するには、サンプル メッセージをテキスト エディターで変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73641-148">You must change the sample messages in a text editor to use other GBIs.</span></span>  
  
 <span data-ttu-id="73641-149">LOBApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) デスクトップ プログラムをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="73641-149">You use the LOBApplication utility to simulate a line-of-business desktop program submitting a message.</span></span> <span data-ttu-id="73641-150">LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="73641-150">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73641-151">参照</span><span class="sxs-lookup"><span data-stu-id="73641-151">See Also</span></span>  
 <span data-ttu-id="73641-152">[ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="73641-152">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="73641-153">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="73641-153">LOBWebApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)