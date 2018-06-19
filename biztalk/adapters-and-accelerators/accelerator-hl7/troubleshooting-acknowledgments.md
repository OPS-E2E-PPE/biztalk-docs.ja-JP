---
title: 受信確認のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecbbb22498cfd3d451c0b8c75c8e6f4502c2364d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207034"
---
# <a name="troubleshooting-acknowledgments"></a><span data-ttu-id="6eefa-102">受信確認のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6eefa-102">Troubleshooting Acknowledgments</span></span>
<span data-ttu-id="6eefa-103">関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] acknowledgments.</span></span>  
  
## <a name="acknowledgments-are-not-generated"></a><span data-ttu-id="6eefa-104">受信確認は生成されません。</span><span class="sxs-lookup"><span data-stu-id="6eefa-104">Acknowledgments are not generated</span></span>  
 <span data-ttu-id="6eefa-105">いない生成されたり、受信確認 (Ack) のいくつかの潜在的な原因があります。</span><span class="sxs-lookup"><span data-stu-id="6eefa-105">There are several potential causes for acknowledgments (ACKs) not being generated or received.</span></span> <span data-ttu-id="6eefa-106">次の潜在的な問題の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-106">Review the following list of potential problems.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6eefa-107">現象</span><span class="sxs-lookup"><span data-stu-id="6eefa-107">Symptom</span></span>  
 <span data-ttu-id="6eefa-108">パーティ情報を更新するときに、受信確認は生成されません[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認を生成するエクスプ ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-108">Acknowledgments are not generated when you update party information in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to generate acknowledgments.</span></span>  
  
<span data-ttu-id="6eefa-109">**考えられる原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をキャッシュし、パーティの構成情報を 15 分ごとに更新します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-109">**Possible cause** : [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] caches and refreshes party configuration information every 15 minutes.</span></span>  
  
<span data-ttu-id="6eefa-110">**解像度**: キャッシュを更新、または再起動には少なくとも 15 分間待機[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]変更がすぐに有効にします。</span><span class="sxs-lookup"><span data-stu-id="6eefa-110">**Resolution** : Wait for at least 15 minutes for the cache to refresh, or restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for changes to take effect immediately.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6eefa-111">現象</span><span class="sxs-lookup"><span data-stu-id="6eefa-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6eefa-112">Ack を生成し、エラー イベントがイベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-112"> does not generate ACKs and event errors appear in the event log.</span></span>  
  
<span data-ttu-id="6eefa-113">**考えられる原因**: ときにバッチの確認を生成できません/メッセージをバッチには、空の FHS11 フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6eefa-113">**Possible cause** : An ACK cannot be generated when a batch in/batch out message contains an empty FHS11 field.</span></span>  
  
<span data-ttu-id="6eefa-114">**解像度**: メッセージが正しく書式設定とデータが設定された FHS11 フィールドを持つことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6eefa-114">**Resolution** : Ensure that your messages have a correctly formatted and populated FHS11 field.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6eefa-115">現象</span><span class="sxs-lookup"><span data-stu-id="6eefa-115">Symptom</span></span>  
 <span data-ttu-id="6eefa-116">アプリケーションが生成または ACK を受信できません。</span><span class="sxs-lookup"><span data-stu-id="6eefa-116">Your application cannot generate or receive an ACK.</span></span>  
  
<span data-ttu-id="6eefa-117">**考えられる原因**: MSH3 フィールドに、メッセージの情報が正しくないように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Ack メッセージを送信するからです。</span><span class="sxs-lookup"><span data-stu-id="6eefa-117">**Possible cause** : Incorrect information in the MSH3 field of your message prevents [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] from sending the message ACKs.</span></span>  
  
<span data-ttu-id="6eefa-118">**解像度**: メッセージが正しく書式設定とデータが設定された MSH3 フィールドを持つことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6eefa-118">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH3 field.</span></span>  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a><span data-ttu-id="6eefa-119">受信確認が一時停止中または送信パーティにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="6eefa-119">Acknowledgments are suspended or not routed to the send party</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6eefa-120">現象</span><span class="sxs-lookup"><span data-stu-id="6eefa-120">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6eefa-121">双方向アダプターの受信確認を生成せずにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-121"> sends messages to a two-way adapter without generating acknowledgments.</span></span>  
  
<span data-ttu-id="6eefa-122">**考えられる原因**: メッセージ サブスクリプションが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="6eefa-122">**Possible cause** : The message subscription is not configured correctly.</span></span>  
  
<span data-ttu-id="6eefa-123">**解像度**: メッセージのサブスクリプションが存在し、構成正しくことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-123">**Resolution** : Ensure that message subscriptions are present and configured correctly.</span></span>  
  
## <a name="suspended-acknowledgments"></a><span data-ttu-id="6eefa-124">中断された受信確認</span><span class="sxs-lookup"><span data-stu-id="6eefa-124">Suspended acknowledgments</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6eefa-125">現象</span><span class="sxs-lookup"><span data-stu-id="6eefa-125">Symptom</span></span>  
 <span data-ttu-id="6eefa-126">「フィールドで見つかった区切り記号」のエラー メッセージで受信確認が中断されているなどの区切り文字が含まれている文字をエンコードしてパーティを構成した場合@-! $ です。</span><span class="sxs-lookup"><span data-stu-id="6eefa-126">Acknowledgments are suspended with the error message "Delimiter found in the field" when you have configured the party to have encoding characters containing delimiter characters such as @-!$.</span></span>  
  
<span data-ttu-id="6eefa-127">**考えられる原因**: メッセージには、ピリオド (.) またはハイフン (-) などの文字が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6eefa-127">**Possible cause** : The message contains characters such as a period (.) or a hyphen (-).</span></span> <span data-ttu-id="6eefa-128">Ack を生成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が含まれています"."と"-"のタイムスタンプ値。</span><span class="sxs-lookup"><span data-stu-id="6eefa-128">When generating the ACKs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] includes "." and "-" for the timestamp value.</span></span>  
  
<span data-ttu-id="6eefa-129">**解像度**: これらのエラーを避けるために、送信パイプラインで検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6eefa-129">**Resolution** : Disable validation in the send pipeline to avoid these errors.</span></span>  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a><span data-ttu-id="6eefa-130">BizTalk Server には、両方向 MLLP アダプターを使用するときに ACK が見つからない場合のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6eefa-130">BizTalk Server generates an error about missing ACK when using 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6eefa-131">現象</span><span class="sxs-lookup"><span data-stu-id="6eefa-131">Symptom</span></span>  
 <span data-ttu-id="6eefa-132">イベント ログに、次のようなエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6eefa-132">You get the following or similar error in the Event Log:</span></span>  
  
 <span data-ttu-id="6eefa-133">"エラーのためのネットワークからの ACK を受信することができません"HRESULT からの例外: 0xC0C01662""</span><span class="sxs-lookup"><span data-stu-id="6eefa-133">"Unable to receive ACK from network due to error "Exception from HRESULT: 0xC0C01662""</span></span>  
  
<span data-ttu-id="6eefa-134">**考えられる原因**: 1 方向を使用している受信し、双方向送信ポートは BizTalk が 2 方向の送信ポートから受信したメッセージを返すの対応する受信ポート。</span><span class="sxs-lookup"><span data-stu-id="6eefa-134">**Possible cause** : You are using 1-way receive and 2-way send port, so BizTalk does not have a corresponding Receive port to return the message received from the 2-way Send port.</span></span>  
  
<span data-ttu-id="6eefa-135">**解像度**: 仕様では、これは、エラー メッセージを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="6eefa-135">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eefa-136">参照</span><span class="sxs-lookup"><span data-stu-id="6eefa-136">See Also</span></span>  
[<span data-ttu-id="6eefa-137">HL7 のトラブルシューティングと既知の問題</span><span class="sxs-lookup"><span data-stu-id="6eefa-137">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)