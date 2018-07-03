---
title: ACK プロセス モデル |Microsoft Docs
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
ms.openlocfilehash: 98fac157c3c3bfa62825fd3c5cb59c68aac528e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970635"
---
# <a name="ack-process-model"></a><span data-ttu-id="27ff3-102">ACK プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="27ff3-102">ACK Process Model</span></span>
<span data-ttu-id="27ff3-103">次の一連の手順では、受信確認 (ACK) プロセス モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-103">The following sequence of steps describes the acknowledgment (ACK) process model:</span></span>  
  
1. <span data-ttu-id="27ff3-104">入学担当者は、患者の入院情報入学システム (ADT) にログをシステムは、トリガー イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-104">When the admissions personnel log patient admission information into the Admissions System (ADT), the system generates a trigger event.</span></span>  
  
2. <span data-ttu-id="27ff3-105">ADT system には、患者の登録の HL7 でエンコードされたメッセージが生成されます (ADT ^ A04) に BizTalk Accelerator for HL7 配信 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="27ff3-105">The ADT system generates an HL7-encoded Patient Registration message (ADT^A04) and delivers it to BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
3. <span data-ttu-id="27ff3-106">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システム ADT で、MLLP ラッパーを適用する ^ A04 メッセージにルーティングし、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン。</span><span class="sxs-lookup"><span data-stu-id="27ff3-106">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system applies an MLLP wrapper on the ADT^A04 message and routes it to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
   -   <span data-ttu-id="27ff3-107">'元のモード' の受信確認の要件が事前構成済み</span><span class="sxs-lookup"><span data-stu-id="27ff3-107">Requirement of 'Original Mode' Acknowledgment is preconfigured</span></span>  
  
   -   <span data-ttu-id="27ff3-108">MSH 15 および 16 null 値を指定します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-108">MSH 15 and 16 have null values</span></span>  
  
4. <span data-ttu-id="27ff3-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンがメッセージを検証し、検証に成功した場合は、ステータスの確認メッセージを生成します**MSA01 = AA**します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the message and if successful validation occurs, it generates the ACK message with the status **MSA01 = AA**.</span></span>  
  
5. <span data-ttu-id="27ff3-110">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン変換 ADT ^ A04 メッセージ MLLP ラッパーで囲むと、ラボ情報システム (LIS) にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="27ff3-110">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine transforms the ADT^A04 message by enclosing it with MLLP wrappers and routing it to the Lab Information System (LIS).</span></span>  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="27ff3-111"> 拡張モード ' の受信確認をあらかじめ</span><span class="sxs-lookup"><span data-stu-id="27ff3-111"> preconfigures 'Enhanced Mode' Acknowledgment</span></span>  
  
   - <span data-ttu-id="27ff3-112">MSH 15 および 16 = AL</span><span class="sxs-lookup"><span data-stu-id="27ff3-112">MSH 15 and 16 = AL</span></span>  
  
6. <span data-ttu-id="27ff3-113">LIS インターフェイス レイヤーがメッセージをコミットして受け入れる ACK の状態を生成するヘッダーを検証します**MSA1 = CA**します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-113">The LIS Interface Layer validates the header by committing the message and generating an ACCEPT ACK with the status **MSA1 = CA**.</span></span> <span data-ttu-id="27ff3-114">インターフェイス層 MLLP ラッパーを使用してメッセージのルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン。</span><span class="sxs-lookup"><span data-stu-id="27ff3-114">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
7. <span data-ttu-id="27ff3-115">LIS インターフェイス レイヤーは、メッセージ全体を検証し、アプリケーション ACK の状態が生成されます**MSA1 = AA**します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-115">The LIS Interface Layer validates the entire message and generates an APPLICATION ACK with the status **MSA1 = AA**.</span></span> <span data-ttu-id="27ff3-116">インターフェイス層 MLLP ラッパーを使用してメッセージのルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン。</span><span class="sxs-lookup"><span data-stu-id="27ff3-116">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="27ff3-117"> あらかじめ 'ACK に必要な'、受信確認の受信確認を行う</span><span class="sxs-lookup"><span data-stu-id="27ff3-117"> preconfigures 'ACK Required' acknowledging the acknowledgment</span></span>  
  
   - <span data-ttu-id="27ff3-118">MSH 15 = AL で、受信側のシステムがコミット Accept メッセージと ACK を確認する必要がありますを示します</span><span class="sxs-lookup"><span data-stu-id="27ff3-118">MSH 15 = AL, which indicates that the receiving system must acknowledge the ACK with a Commit Accept Message</span></span>  
  
8. <span data-ttu-id="27ff3-119">LIS インターフェイス レイヤーは、形式の要件に従って、アプリケーション層にメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-119">The LIS Interface layer delivers the message to the Application Layer in accordance with the format requirement.</span></span>  
  
9. <span data-ttu-id="27ff3-120">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、(前の手順 7.) 内の LIS インターフェイス レイヤーから受信した ACK を検証し、ステータスの LIS インターフェイス レイヤーに ACK で応答**MSA1 = CA**します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-120">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the ACK received from the LIS Interface Layer (in step 7 above) and responds with an ACK back to the LIS Interface Layer with the status **MSA1= CA**.</span></span>  
  
10. <span data-ttu-id="27ff3-121">LIS システムのユーザーは、患者の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="27ff3-121">A user of the LIS System reviews the Patient information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ff3-122">参照</span><span class="sxs-lookup"><span data-stu-id="27ff3-122">See Also</span></span>  
 <span data-ttu-id="27ff3-123">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="27ff3-123">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="27ff3-124">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="27ff3-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)