---
title: ACK 処理モデル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846ecf4d8eee4eca0e8a75a3444a1478b7db5910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205922"
---
# <a name="ack-process-model"></a><span data-ttu-id="db2ee-102">ACK プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="db2ee-102">ACK Process Model</span></span>
<span data-ttu-id="db2ee-103">次の一連の手順では、受信確認 (ACK) プロセス モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="db2ee-103">The following sequence of steps describes the acknowledgment (ACK) process model:</span></span>  
  
1.  <span data-ttu-id="db2ee-104">受付担当者ログオンと受付の患者情報受付システム (ADT) に、システムは、トリガー イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="db2ee-104">When the admissions personnel log patient admission information into the Admissions System (ADT), the system generates a trigger event.</span></span>  
  
2.  <span data-ttu-id="db2ee-105">ADT システムの患者情報登録の HL7 でエンコードされたメッセージが生成されます (ADT ^ A04) しに BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="db2ee-105">The ADT system generates an HL7-encoded Patient Registration message (ADT^A04) and delivers it to BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
3.  <span data-ttu-id="db2ee-106">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システム、ADT に MLLP ラッパーを適用する ^ A04 メッセージ ルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンです。</span><span class="sxs-lookup"><span data-stu-id="db2ee-106">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system applies an MLLP wrapper on the ADT^A04 message and routes it to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
    -   <span data-ttu-id="db2ee-107">'元のモード' の受信確認の要件が事前に構成します。</span><span class="sxs-lookup"><span data-stu-id="db2ee-107">Requirement of 'Original Mode' Acknowledgment is preconfigured</span></span>  
  
    -   <span data-ttu-id="db2ee-108">MSH 15、16 null 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="db2ee-108">MSH 15 and 16 have null values</span></span>  
  
4.  <span data-ttu-id="db2ee-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンがメッセージを検証し、検証が成功した場合は、ステータスの確認メッセージが生成されます**MSA01 AA =** です。</span><span class="sxs-lookup"><span data-stu-id="db2ee-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the message and if successful validation occurs, it generates the ACK message with the status **MSA01 = AA**.</span></span>  
  
5.  <span data-ttu-id="db2ee-110">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン変換、ADT ^ MLLP ラッパーで囲むと、ラボ情報システム (LIS) へのルーティングでメッセージを A04 です。</span><span class="sxs-lookup"><span data-stu-id="db2ee-110">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine transforms the ADT^A04 message by enclosing it with MLLP wrappers and routing it to the Lab Information System (LIS).</span></span>  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="db2ee-111">'拡張モード' の受信確認をあらかじめ構成しておきます</span><span class="sxs-lookup"><span data-stu-id="db2ee-111"> preconfigures 'Enhanced Mode' Acknowledgment</span></span>  
  
    -   <span data-ttu-id="db2ee-112">MSH 15、16 AL を =</span><span class="sxs-lookup"><span data-stu-id="db2ee-112">MSH 15 and 16 = AL</span></span>  
  
6.  <span data-ttu-id="db2ee-113">LIS インターフェイス レイヤーがメッセージをコミットして受け入れる ACK の状態を生成するヘッダーを検証**MSA1 = CA**です。</span><span class="sxs-lookup"><span data-stu-id="db2ee-113">The LIS Interface Layer validates the header by committing the message and generating an ACCEPT ACK with the status **MSA1 = CA**.</span></span> <span data-ttu-id="db2ee-114">インターフェイス レイヤーが MLLP のラッパーを持つメッセージをルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンです。</span><span class="sxs-lookup"><span data-stu-id="db2ee-114">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
7.  <span data-ttu-id="db2ee-115">LIS インターフェイス層は、メッセージ全体を検証し、アプリケーション ACK の状態が生成されます**MSA1 AA =** です。</span><span class="sxs-lookup"><span data-stu-id="db2ee-115">The LIS Interface Layer validates the entire message and generates an APPLICATION ACK with the status **MSA1 = AA**.</span></span> <span data-ttu-id="db2ee-116">インターフェイス レイヤーが MLLP のラッパーを持つメッセージをルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンです。</span><span class="sxs-lookup"><span data-stu-id="db2ee-116">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="db2ee-117">'確認が必要'、受信確認の受信確認をあらかじめ構成しておきます</span><span class="sxs-lookup"><span data-stu-id="db2ee-117"> preconfigures 'ACK Required' acknowledging the acknowledgment</span></span>  
  
    -   <span data-ttu-id="db2ee-118">MSH 15 = AL で、受信側のシステムがコミット Accept メッセージと ACK を確認する必要がありますを示します</span><span class="sxs-lookup"><span data-stu-id="db2ee-118">MSH 15 = AL, which indicates that the receiving system must acknowledge the ACK with a Commit Accept Message</span></span>  
  
8.  <span data-ttu-id="db2ee-119">LIS インターフェイス層は、形式の要件に従って、アプリケーション層にメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="db2ee-119">The LIS Interface layer delivers the message to the Application Layer in accordance with the format requirement.</span></span>  
  
9. <span data-ttu-id="db2ee-120">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン LIS インターフェイス レイヤー (手順 7. 上) から受信した確認を検証し、ステータスの LIS インターフェイス レイヤーに ACK で応答**MSA1 = CA**です。</span><span class="sxs-lookup"><span data-stu-id="db2ee-120">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the ACK received from the LIS Interface Layer (in step 7 above) and responds with an ACK back to the LIS Interface Layer with the status **MSA1= CA**.</span></span>  
  
10. <span data-ttu-id="db2ee-121">LIS システムのユーザーは、患者の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="db2ee-121">A user of the LIS System reviews the Patient information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2ee-122">参照</span><span class="sxs-lookup"><span data-stu-id="db2ee-122">See Also</span></span>  
 <span data-ttu-id="db2ee-123">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="db2ee-123">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="db2ee-124">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="db2ee-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)