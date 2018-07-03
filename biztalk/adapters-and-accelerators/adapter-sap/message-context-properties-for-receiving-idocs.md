---
title: Idoc を受信するためのメッセージ コンテキスト プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f99c403648ec2fae7fd9ee93f349f7c1fe69434
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999803"
---
# <a name="message-context-properties-for-receiving-idocs"></a><span data-ttu-id="beed8-102">Idoc を受信するためのメッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="beed8-102">Message Context Properties for Receiving IDOCs</span></span>
<span data-ttu-id="beed8-103">Microsoft を使用して IDOC を受信するため[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のメッセージ コンテキスト プロパティがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="beed8-103">For receiving an IDOC using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
 <span data-ttu-id="beed8-104">**IDOC 制御レコードのプロパティです。**</span><span class="sxs-lookup"><span data-stu-id="beed8-104">**IDOC Control Record properties.**</span></span>  
  
- <span data-ttu-id="beed8-105">**TABNAM** -テーブルの構造体の名前</span><span class="sxs-lookup"><span data-stu-id="beed8-105">**TABNAM** - Name of table structure</span></span>  
  
- <span data-ttu-id="beed8-106">**MANDT** -クライアント</span><span class="sxs-lookup"><span data-stu-id="beed8-106">**MANDT** - Client</span></span>  
  
- <span data-ttu-id="beed8-107">**DOCNUM** -IDOC 番号</span><span class="sxs-lookup"><span data-stu-id="beed8-107">**DOCNUM** - IDOC number</span></span>  
  
- <span data-ttu-id="beed8-108">**DOCREL** -IDOC を SAP リリース</span><span class="sxs-lookup"><span data-stu-id="beed8-108">**DOCREL** - SAP Release for IDOC</span></span>  
  
- <span data-ttu-id="beed8-109">**ステータス**の IDOC の状態</span><span class="sxs-lookup"><span data-stu-id="beed8-109">**STATUS** - Status of IDOC</span></span>  
  
- <span data-ttu-id="beed8-110">**直接**-の方向</span><span class="sxs-lookup"><span data-stu-id="beed8-110">**DIRECT** - Direction</span></span>  
  
- <span data-ttu-id="beed8-111">**OUTMOD** -出力モード</span><span class="sxs-lookup"><span data-stu-id="beed8-111">**OUTMOD** - Output mode</span></span>  
  
- <span data-ttu-id="beed8-112">**表現**- 受信処理にオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="beed8-112">**EXPRSS** - Overriding in inbound processing</span></span>  
  
- <span data-ttu-id="beed8-113">**テスト**-フラグをテストします。</span><span class="sxs-lookup"><span data-stu-id="beed8-113">**TEST** - Test flag</span></span>  
  
- <span data-ttu-id="beed8-114">**IDOCTYP** -基本的な型の名前</span><span class="sxs-lookup"><span data-stu-id="beed8-114">**IDOCTYP** - Name of basic type</span></span>  
  
- <span data-ttu-id="beed8-115">**CIMTYP** -拡張機能 (顧客によって定義される)</span><span class="sxs-lookup"><span data-stu-id="beed8-115">**CIMTYP** - Extension (defined by customer)</span></span>  
  
- <span data-ttu-id="beed8-116">**MESTYP** -メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="beed8-116">**MESTYP** - Message type</span></span>  
  
- <span data-ttu-id="beed8-117">**MESCOD** -メッセージ コード</span><span class="sxs-lookup"><span data-stu-id="beed8-117">**MESCOD** - Message code</span></span>  
  
- <span data-ttu-id="beed8-118">**MESFCT** -メッセージの関数</span><span class="sxs-lookup"><span data-stu-id="beed8-118">**MESFCT** - Message function</span></span>  
  
- <span data-ttu-id="beed8-119">**STD** -EDI 標準、フラグ</span><span class="sxs-lookup"><span data-stu-id="beed8-119">**STD** - EDI standard, flag</span></span>  
  
- <span data-ttu-id="beed8-120">**STDVRS** -EDI、標準のバージョンとリリース</span><span class="sxs-lookup"><span data-stu-id="beed8-120">**STDVRS** - EDI standard, version and release</span></span>  
  
- <span data-ttu-id="beed8-121">**STDMES** -EDI メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="beed8-121">**STDMES** - EDI message type</span></span>  
  
- <span data-ttu-id="beed8-122">**SNDPOR** -送信者のポート (SAP システムの外部のサブシステム)</span><span class="sxs-lookup"><span data-stu-id="beed8-122">**SNDPOR** - Sender port (SAP System, external subsystem)</span></span>  
  
- <span data-ttu-id="beed8-123">**SNDPRT** -パートナーの送信者の種類</span><span class="sxs-lookup"><span data-stu-id="beed8-123">**SNDPRT** - Partner type of sender</span></span>  
  
- <span data-ttu-id="beed8-124">**SNDPFC** -パートナーの送信元の関数</span><span class="sxs-lookup"><span data-stu-id="beed8-124">**SNDPFC** - Partner Function of Sender</span></span>  
  
- <span data-ttu-id="beed8-125">**SNDPRN** -パートナーの送信側の数</span><span class="sxs-lookup"><span data-stu-id="beed8-125">**SNDPRN** - Partner Number of Sender</span></span>  
  
- <span data-ttu-id="beed8-126">**SNDSAD** -センダのアドレス (SADR)</span><span class="sxs-lookup"><span data-stu-id="beed8-126">**SNDSAD** - Sender address (SADR)</span></span>  
  
- <span data-ttu-id="beed8-127">**SNDLAD** -送信者の論理アドレス</span><span class="sxs-lookup"><span data-stu-id="beed8-127">**SNDLAD** - Logical address of sender</span></span>  
  
- <span data-ttu-id="beed8-128">**RCVPOR** -受信ポート</span><span class="sxs-lookup"><span data-stu-id="beed8-128">**RCVPOR** - Receiver port</span></span>  
  
- <span data-ttu-id="beed8-129">**RCVPRT** -受信者のパートナーの種類</span><span class="sxs-lookup"><span data-stu-id="beed8-129">**RCVPRT** - Partner Type of receiver</span></span>  
  
- <span data-ttu-id="beed8-130">**RCVPFC** -パートナーの受信者の関数</span><span class="sxs-lookup"><span data-stu-id="beed8-130">**RCVPFC** - Partner function of recipient</span></span>  
  
- <span data-ttu-id="beed8-131">**RCVPRN** -パートナーの受信者の数</span><span class="sxs-lookup"><span data-stu-id="beed8-131">**RCVPRN** - Partner number of recipient</span></span>  
  
- <span data-ttu-id="beed8-132">**RCVSAD** -受信者のアドレス (SADR)</span><span class="sxs-lookup"><span data-stu-id="beed8-132">**RCVSAD** - Recipient address (SADR)</span></span>  
  
- <span data-ttu-id="beed8-133">**RCVLAD** -受信者の論理アドレス</span><span class="sxs-lookup"><span data-stu-id="beed8-133">**RCVLAD** - Logical address of recipient</span></span>  
  
- <span data-ttu-id="beed8-134">**CREDAT** - の作成</span><span class="sxs-lookup"><span data-stu-id="beed8-134">**CREDAT** - Created on</span></span>  
  
- <span data-ttu-id="beed8-135">**CRETIM** -作成された時刻</span><span class="sxs-lookup"><span data-stu-id="beed8-135">**CRETIM** - Time Created</span></span>  
  
- <span data-ttu-id="beed8-136">**REFINT** -転送のファイル (EDI インターチェンジ)</span><span class="sxs-lookup"><span data-stu-id="beed8-136">**REFINT** - Transmission file (EDI Interchange)</span></span>  
  
- <span data-ttu-id="beed8-137">**REFGRP** -メッセージのグループ (EDI メッセージのグループ)</span><span class="sxs-lookup"><span data-stu-id="beed8-137">**REFGRP** - Message group (EDI Message Group)</span></span>  
  
- <span data-ttu-id="beed8-138">**REFMES** -メッセージ (EDI メッセージ)</span><span class="sxs-lookup"><span data-stu-id="beed8-138">**REFMES** - Message (EDI Message)</span></span>  
  
- <span data-ttu-id="beed8-139">**ARCKEY** - 外部メッセージのアーカイブのキー</span><span class="sxs-lookup"><span data-stu-id="beed8-139">**ARCKEY** - Key for external message archive</span></span>  
  
- <span data-ttu-id="beed8-140">**シリアル**-シリアル化</span><span class="sxs-lookup"><span data-stu-id="beed8-140">**SERIAL** - Serialization</span></span>  
  
- <span data-ttu-id="beed8-141">**DOCTYP**の IDOC の種類 (この EDI_DC で使用できるだけです。</span><span class="sxs-lookup"><span data-stu-id="beed8-141">**DOCTYP** - IDOC type (This is available in EDI_DC only.</span></span> <span data-ttu-id="beed8-142">コンテキスト プロパティに存在する必要がありますが、2 の Idoc のバージョンののみ昇格する必要があります)</span><span class="sxs-lookup"><span data-stu-id="beed8-142">Should be present in the context property but should be promoted for Version 2 IDOCs only)</span></span>  
  
  <span data-ttu-id="beed8-143">**TID** – 受信 TRFC 呼び出しの SAP システムから送信された TID を表します。</span><span class="sxs-lookup"><span data-stu-id="beed8-143">**TID** – Represents the TID sent by the SAP system for the incoming TRFC call.</span></span>  
  
  <span data-ttu-id="beed8-144">**GUID** : GUID を表します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="beed8-144">**GUID** – Represents the GUID which the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses internally.</span></span> <span data-ttu-id="beed8-145">これは、SAP システムから受け取った TID で一対一のマッピングがあります。</span><span class="sxs-lookup"><span data-stu-id="beed8-145">This has a one-to-one mapping with the TID which was received from the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beed8-146">参照</span><span class="sxs-lookup"><span data-stu-id="beed8-146">See Also</span></span>  
 [<span data-ttu-id="beed8-147">メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="beed8-147">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)