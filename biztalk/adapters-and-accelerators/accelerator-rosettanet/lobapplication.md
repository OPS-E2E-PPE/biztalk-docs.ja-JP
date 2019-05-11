---
title: LOBApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3f65980015d689cd79f1d006441c1687d15be01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283328"
---
# <a name="lobapplication"></a><span data-ttu-id="6edbf-102">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="6edbf-102">LOBApplication</span></span>
<span data-ttu-id="6edbf-103">実際の基幹業務 (LOB) デスクトップ プログラムをシミュレートする取引先のアクションまたは応答メッセージを送信するのにには、LOBApplication ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-103">You use the LOBApplication utility to submit an action or response message to a trading partner, simulating an actual line-of-business (LOB) desktop program.</span></span>  
  
 <span data-ttu-id="6edbf-104">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]サンプル メッセージを提供します、 \<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6edbf-104">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides sample messages in the \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="6edbf-105">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="6edbf-105">Location in SDK</span></span>  
 <span data-ttu-id="6edbf-106">\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication</span><span class="sxs-lookup"><span data-stu-id="6edbf-106">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication</span></span>  
  
## <a name="running-lobapplication"></a><span data-ttu-id="6edbf-107">LOBApplication の実行</span><span class="sxs-lookup"><span data-stu-id="6edbf-107">Running LOBApplication</span></span>  
  
#### <a name="to-run-lobapplication"></a><span data-ttu-id="6edbf-108">LOBApplication を実行するには</span><span class="sxs-lookup"><span data-stu-id="6edbf-108">To run LOBApplication</span></span>  
  
1.  <span data-ttu-id="6edbf-109">Windows エクスプ ローラーで、移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-109">In Windows Explorer, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
2.  <span data-ttu-id="6edbf-110">ダブルクリック**LOBApplication.exe**、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-110">Double-click **LOBApplication.exe**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="6edbf-111">次のページでは、ユーティリティを実行するために必要な情報の表示します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-111">The pages that follow prompt you for the information that is required to run the utility.</span></span>  
  
## <a name="syntax-for-lobapplication"></a><span data-ttu-id="6edbf-112">LOBApplication の構文</span><span class="sxs-lookup"><span data-stu-id="6edbf-112">Syntax for LOBApplication</span></span>  
 <span data-ttu-id="6edbf-113">使用して、 **LOB Application**ページをホームとパートナーの名前、プロセス PIP (Partner Interface) のプロパティ、および LOBApplication ユーティリティによって送信されたメッセージのメッセージのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-113">Use the **LOB Application Proxy** page to specify home and partner names, Partner Interface Process (PIP) properties, and message properties for the message sent by the LOBApplication utility.</span></span>  
  
 <span data-ttu-id="6edbf-114">次の表に、各フィールドの使用方法、 **LOB Application**ページ。</span><span class="sxs-lookup"><span data-stu-id="6edbf-114">The following table describes how to use each field on the **LOB Application Proxy** page.</span></span>  
  
|<span data-ttu-id="6edbf-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6edbf-115">Use this</span></span>|<span data-ttu-id="6edbf-116">目的</span><span class="sxs-lookup"><span data-stu-id="6edbf-116">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6edbf-117">**Home Profile Name**</span><span class="sxs-lookup"><span data-stu-id="6edbf-117">**Home Profile Name**</span></span>|<span data-ttu-id="6edbf-118">ホーム組織 (送信元パーティ) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-118">Type the name of the home organization (source party).</span></span>|  
|<span data-ttu-id="6edbf-119">**取引先名**</span><span class="sxs-lookup"><span data-stu-id="6edbf-119">**Trading Partner Name**</span></span>|<span data-ttu-id="6edbf-120">取引先 (送信先パーティ) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-120">Type the name of the trading partner (destination party).</span></span>|  
|<span data-ttu-id="6edbf-121">**PIP の名前**</span><span class="sxs-lookup"><span data-stu-id="6edbf-121">**PIP Name**</span></span>|<span data-ttu-id="6edbf-122">入力の種類」などの PIP 表示コード**3 a 2**します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-122">Type the display code of the PIP, for example, type **3A2**.</span></span> <span data-ttu-id="6edbf-123">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6edbf-123">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="6edbf-124">**[PIP Version]**</span><span class="sxs-lookup"><span data-stu-id="6edbf-124">**PIP Version**</span></span>|<span data-ttu-id="6edbf-125">入力の種類」などの PIP のバージョン**V02.00**します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-125">Type the version of the PIP, for example, type **V02.00**.</span></span> <span data-ttu-id="6edbf-126">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6edbf-126">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="6edbf-127">**PIP インスタンス ID** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="6edbf-127">**PIP Instance ID** (optional)</span></span>|<span data-ttu-id="6edbf-128">たとえば、入力、PIP の英数字のインスタンス ID を入力**STD_3A2_V02.02**します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-128">Type an alphanumeric instance ID for the PIP, for example, type **STD_3A2_V02.02**.</span></span> <span data-ttu-id="6edbf-129">特殊文字を避けてください。</span><span class="sxs-lookup"><span data-stu-id="6edbf-129">Avoid special characters.</span></span> <span data-ttu-id="6edbf-130">ID は、取引先および PIP コードごとに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6edbf-130">The ID should be unique per partner and per PIP code.</span></span> <span data-ttu-id="6edbf-131">LOBApplication ユーティリティはメッセージとしてマークされているアクションのメッセージ場合は、インスタンス ID は空の場合、PIP インスタンス id、生成された HUID 値を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6edbf-131">For messages that are marked as action messages, if the Instance ID is empty, the LOBApplication utility uses a generated HUID value for the PIP Instance ID.</span></span> <span data-ttu-id="6edbf-132">**注:** 選択すると**応答**で、**メッセージ カテゴリ**、PIP インスタンス ID は、このフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6edbf-132">**Note:**  When you select **Response** in the **Message Category**, you must type the PIP Instance ID in this field.</span></span>|  
|<span data-ttu-id="6edbf-133">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="6edbf-133">**File Name**</span></span>|<span data-ttu-id="6edbf-134">省略記号ボタン (…) をクリックして、PIP インスタンス ファイルを含むフォルダーに移動し、PIP インスタンス ファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6edbf-134">Click the ellipsis button (...), go to the folder that contains the PIP instance file, and then click the PIP instance file.</span></span>|  
|<span data-ttu-id="6edbf-135">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="6edbf-135">**Message Category**</span></span>|<span data-ttu-id="6edbf-136">メッセージの種類を選択します (**アクション**または**応答**)。</span><span class="sxs-lookup"><span data-stu-id="6edbf-136">Select the type of message (**Action** or **Response**).</span></span>|  
|<span data-ttu-id="6edbf-137">**[Attachments]**</span><span class="sxs-lookup"><span data-stu-id="6edbf-137">**Attachments**</span></span>|<span data-ttu-id="6edbf-138">クリックして**追加**、添付ファイルを含むフォルダーに移動し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-138">Click **Add**, move to the folder that contains the attachment file, and then click **Open**.</span></span>|  
|<span data-ttu-id="6edbf-139">**メッセージを送信します。**</span><span class="sxs-lookup"><span data-stu-id="6edbf-139">**Submit Message**</span></span>|<span data-ttu-id="6edbf-140">メッセージを送信する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6edbf-140">Click to send the message.</span></span>|  
|<span data-ttu-id="6edbf-141">**ステータス**</span><span class="sxs-lookup"><span data-stu-id="6edbf-141">**Status**</span></span>|<span data-ttu-id="6edbf-142">このフィールド内のアクションの状態を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6edbf-142">Read the status of the action in this field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6edbf-143">コメント</span><span class="sxs-lookup"><span data-stu-id="6edbf-143">Remarks</span></span>  
 <span data-ttu-id="6edbf-144">LOBApplication ユーティリティは、指定すると、プロパティを持つメッセージを作成し、取引先パートナーに送信します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-144">The LOBApplication utility creates a message with the properties specified, and sends it to the trading partner.</span></span> <span data-ttu-id="6edbf-145">このユーティリティは、メッセージの service content データを BTARNDATA データベースの MessageFromLOB テーブルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6edbf-145">This utility writes the service content data in the message to the BTARNDATA database, in the MessageFromLOB table.</span></span> <span data-ttu-id="6edbf-146">このユーティリティは、アクション メッセージの送信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="6edbf-146">This utility simulates sending an action message.</span></span>  
  
 <span data-ttu-id="6edbf-147">LOBApplication フォルダー下の SampleInstances フォルダーにサンプル メッセージ、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK は次のグローバル ビジネス識別子 (Gbi) と仮定する事前構成済み。ホーム組織とパートナー組織に対して 987654321 123456789 します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-147">The sample messages in the SampleInstances folder under the LOBApplication folder in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK are preconfigured to assume the following Global Business Identifiers (GBIs): 123456789 for the home organization and 987654321 for the partner organization.</span></span> <span data-ttu-id="6edbf-148">以外の Gbi を使用するテキスト エディターで、サンプル メッセージを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6edbf-148">You must change the sample messages in a text editor to use other GBIs.</span></span>  
  
 <span data-ttu-id="6edbf-149">メッセージを送信する基幹業務デスクトップ プログラムをシミュレートするのにには、LOBApplication ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-149">You use the LOBApplication utility to simulate a line-of-business desktop program submitting a message.</span></span> <span data-ttu-id="6edbf-150">LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="6edbf-150">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6edbf-151">参照</span><span class="sxs-lookup"><span data-stu-id="6edbf-151">See Also</span></span>  
 <span data-ttu-id="6edbf-152">[ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="6edbf-152">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="6edbf-153">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="6edbf-153">LOBWebApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
