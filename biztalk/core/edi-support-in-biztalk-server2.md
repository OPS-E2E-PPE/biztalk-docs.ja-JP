---
title: EDI のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b1c7ba658d3f7921fb0a96b25c06d18e45e81d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350217"
---
# <a name="edi-support-in-biztalk-server"></a><span data-ttu-id="cb9ff-102">BizTalk Server における EDI のサポート</span><span class="sxs-lookup"><span data-stu-id="cb9ff-102">EDI Support in BizTalk Server</span></span>
<span data-ttu-id="cb9ff-103">EDI が、BizTalk Server に組み込まれておよびオプションのコンポーネントをインストールして、BizTalk Server を構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-103">EDI is built-in to BizTalk Server, and is an optional component when you install and configure BizTalk Server.</span></span> 
  
## <a name="feature-set-comparison-chart"></a><span data-ttu-id="cb9ff-104">機能セットの比較表</span><span class="sxs-lookup"><span data-stu-id="cb9ff-104">Feature Set Comparison Chart</span></span>  
 <span data-ttu-id="cb9ff-105">次の表では、BizTalk Server に付属する EDI のサポートを示します。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-105">The following table shows the EDI support included with BizTalk Server.</span></span>
  
|<span data-ttu-id="cb9ff-106">機能</span><span class="sxs-lookup"><span data-stu-id="cb9ff-106">Feature</span></span>|<span data-ttu-id="cb9ff-107">解説</span><span class="sxs-lookup"><span data-stu-id="cb9ff-107">Comment</span></span>|  
|---|---|
|<span data-ttu-id="cb9ff-108">トランザクション セットでの ISA セグメントの変更</span><span class="sxs-lookup"><span data-stu-id="cb9ff-108">ISA    Segment modification at transaction set</span></span>| <span data-ttu-id="cb9ff-109">トランザクション セット固有の契約を作成します。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-109">Create TransactionSet-specific agreements</span></span>|  
|<span data-ttu-id="cb9ff-110">ISA11:  米国またはその他の標準の型</span><span class="sxs-lookup"><span data-stu-id="cb9ff-110">ISA11:    US or other standard type</span></span>| |  
|<span data-ttu-id="cb9ff-111">[ISA12]:  インターチェンジ制御バージョン</span><span class="sxs-lookup"><span data-stu-id="cb9ff-111">ISA12:    Interchange Control Version</span></span>| |  
|<span data-ttu-id="cb9ff-112">ISA 13:  インターチェンジ制御番号が (番号の増分)</span><span class="sxs-lookup"><span data-stu-id="cb9ff-112">ISA13:    Interchange Control Number (incrementing number)</span></span>| |  
|<span data-ttu-id="cb9ff-113">ISA 15:  テストまたは実稼働</span><span class="sxs-lookup"><span data-stu-id="cb9ff-113">ISA15:    Test or Production</span></span>| |  
|<span data-ttu-id="cb9ff-114">ドキュメント/トランザクション レベルでの GS セグメントの変更</span><span class="sxs-lookup"><span data-stu-id="cb9ff-114">GS    Segment modification at document/transaction level</span></span>| |  
|<span data-ttu-id="cb9ff-115">ISA と異なる GS 送信者/受信者 Id の許可</span><span class="sxs-lookup"><span data-stu-id="cb9ff-115">GS    sender/receiver IDs allowed to be different than ISA</span></span>| |  
|<span data-ttu-id="cb9ff-116">ISA および GS の送信 Id と異なる受信のドキュメント Id</span><span class="sxs-lookup"><span data-stu-id="cb9ff-116">Inbound    Document IDs different than ISA & GS Outbound IDs</span></span>| |  
|<span data-ttu-id="cb9ff-117">GS01:  ドキュメントの種類を変更する機能</span><span class="sxs-lookup"><span data-stu-id="cb9ff-117">GS01:    Ability to change type of document</span></span>| |  
|<span data-ttu-id="cb9ff-118">GS04:  日付 (形式を変更する機能)</span><span class="sxs-lookup"><span data-stu-id="cb9ff-118">GS04:    Date (Ability to change format)</span></span>|<span data-ttu-id="cb9ff-119">CCYYMMDD および YYMMDD の形式を選択するための UI が含まれています</span><span class="sxs-lookup"><span data-stu-id="cb9ff-119">Contains UI to select format as CCYYMMDD and YYMMDD</span></span>|  
|<span data-ttu-id="cb9ff-120">GS05:  時刻 (形式を変更する機能)</span><span class="sxs-lookup"><span data-stu-id="cb9ff-120">GS05:    Time (Ability to change format)</span></span>|<span data-ttu-id="cb9ff-121">HHMM、HHMMSS、および HHMMSSdd の形式を選択するための UI が含まれています</span><span class="sxs-lookup"><span data-stu-id="cb9ff-121">Contains UI to select format as HHMM, HHMMSS, and HHMMSSdd</span></span>|  
|<span data-ttu-id="cb9ff-122">GS06:  制御番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-122">GS06:    Change the control number</span></span>| |  
|<span data-ttu-id="cb9ff-123">GS07:  機関コード</span><span class="sxs-lookup"><span data-stu-id="cb9ff-123">GS07:    Agency Code</span></span>| |  
|<span data-ttu-id="cb9ff-124">GS08:  標準のバージョンでの挿入</span><span class="sxs-lookup"><span data-stu-id="cb9ff-124">GS08:    Able to put in standards version</span></span>| |  
|<span data-ttu-id="cb9ff-125">実行時に EDI エンベロープをオーバーライドする機能</span><span class="sxs-lookup"><span data-stu-id="cb9ff-125">Ability to override EDI envelope at runtime</span></span>| |  
|<span data-ttu-id="cb9ff-126">カスタム EDI スキーマ</span><span class="sxs-lookup"><span data-stu-id="cb9ff-126">Custom    EDI Schemas</span></span>| |  
|<span data-ttu-id="cb9ff-127">組織/パーティの設定</span><span class="sxs-lookup"><span data-stu-id="cb9ff-127">Organization/Party Setting</span></span>|<span data-ttu-id="cb9ff-128">別のパーティとアグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-128">Create separate party and agreements.</span></span> <span data-ttu-id="cb9ff-129">テンプレートに基づいてアグリーメントを作成もできます。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-129">Also create agreements based off templates.</span></span>|  
|<span data-ttu-id="cb9ff-130">EDI ドキュメントのドキュメント定義を介したルーティング</span><span class="sxs-lookup"><span data-stu-id="cb9ff-130">EDI    document routing via document definition</span></span>| |  
|<span data-ttu-id="cb9ff-131">取引先への自動 997</span><span class="sxs-lookup"><span data-stu-id="cb9ff-131">Automatic 997’s to trading partners</span></span>|<span data-ttu-id="cb9ff-132">ビジネス プロファイルに固有の構成</span><span class="sxs-lookup"><span data-stu-id="cb9ff-132">Configuration specific to business profiles</span></span>|  
|<span data-ttu-id="cb9ff-133">信頼性の高いメッセージング 997 経由で送信 EDI</span><span class="sxs-lookup"><span data-stu-id="cb9ff-133">Outbound    EDI reliable messaging via 997’s</span></span>| |  
|<span data-ttu-id="cb9ff-134">EDIFACT のサポート</span><span class="sxs-lookup"><span data-stu-id="cb9ff-134">EDIFACT    Support</span></span>|<span data-ttu-id="cb9ff-135">ISO 9735 v4.1 D93 D05 をサポートしています</span><span class="sxs-lookup"><span data-stu-id="cb9ff-135">Supports D93 to D05 per ISO 9735 v4.1</span></span>|  
|<span data-ttu-id="cb9ff-136">X12 サポートします。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-136">X12    Support</span></span>|<span data-ttu-id="cb9ff-137">2040 5030 がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-137">2040 to 5030</span></span>|  
|<span data-ttu-id="cb9ff-138">HIPAA のサポート</span><span class="sxs-lookup"><span data-stu-id="cb9ff-138">HIPAA support</span></span>| <span data-ttu-id="cb9ff-139">Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) ネイティブの EDI 機能の一部として</span><span class="sxs-lookup"><span data-stu-id="cb9ff-139">Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) as  part of native EDI functionality</span></span>|  
|<span data-ttu-id="cb9ff-140">列挙子/コードリストの削除機能</span><span class="sxs-lookup"><span data-stu-id="cb9ff-140">Ability to remove enumerators/codelists</span></span>|<span data-ttu-id="cb9ff-141">Visual Studio/biztalk エディターを使用して</span><span class="sxs-lookup"><span data-stu-id="cb9ff-141">Use Visual Studio/BizTalk Editor</span></span>|  
|<span data-ttu-id="cb9ff-142">AS2 の送信/受信</span><span class="sxs-lookup"><span data-stu-id="cb9ff-142">AS2    Send/Receive</span></span>| <span data-ttu-id="cb9ff-143">AS2 は複数ファイルの添付ファイルのサポート、ファイル名の保持のサポート、および相互運用性です。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-143">AS2 is Drummond Certified for multi-file attachment support, file name preservation support and interoperability.</span></span>|  
|<span data-ttu-id="cb9ff-144">AS2 ファイル名の保持</span><span class="sxs-lookup"><span data-stu-id="cb9ff-144">AS2 file name preservation</span></span>| |  
|<span data-ttu-id="cb9ff-145">AS2 の信頼できるメッセージング</span><span class="sxs-lookup"><span data-stu-id="cb9ff-145">AS2 reliable messaging</span></span>| |  
|<span data-ttu-id="cb9ff-146">送信バッチ処理が (複数の種類のトランザクションを 1 つのトランザクションにまとめる)</span><span class="sxs-lookup"><span data-stu-id="cb9ff-146">Outbound    Batching (accumulating multiple transaction types in a single transaction)</span></span>|<span data-ttu-id="cb9ff-147">各ビジネス プロファイルについて複数のバッチ構成をサポートしています</span><span class="sxs-lookup"><span data-stu-id="cb9ff-147">Supports multiple batch configurations for each business profile</span></span>|  
|<span data-ttu-id="cb9ff-148">バッチ処理-インターチェンジの受信 ("バッチ化された"受信インターチェンジを保存する) XML または構成オプションに基づいてトランザクション セット XML</span><span class="sxs-lookup"><span data-stu-id="cb9ff-148">Inbound    Batching – Interchange XML (preserving an incoming ‘batched’ interchange) or Transaction Set XML based off configuration options</span></span>|<span data-ttu-id="cb9ff-149">受信のバッチ解除、つまり、個々 のトランザクション セット Xml にインターチェンジの分割もサポートします。</span><span class="sxs-lookup"><span data-stu-id="cb9ff-149">Also supports inbound-debatching, i.e., splitting interchange into individual Transaction Set Xml</span></span>|  
|<span data-ttu-id="cb9ff-150">インターチェンジおよびトランザクション セットの生成と検証 Visual Studio でデザイン時</span><span class="sxs-lookup"><span data-stu-id="cb9ff-150">Interchange    and Transaction Set Generation and Validation in Design Time in Visual Studio</span></span>| |  
|<span data-ttu-id="cb9ff-151">TA1 (技術確認) の生成と調整</span><span class="sxs-lookup"><span data-stu-id="cb9ff-151">TA1    (Technical ACK) Generation and Reconciliation</span></span>| |  
|<span data-ttu-id="cb9ff-152">省略可能な EDI および XSD 検証フラグ</span><span class="sxs-lookup"><span data-stu-id="cb9ff-152">Optional    EDI and XSD Validation flags</span></span>| |  
|<span data-ttu-id="cb9ff-153">GS レベルでのドキュメントの形式と定義</span><span class="sxs-lookup"><span data-stu-id="cb9ff-153">Document    format/definition at GS level</span></span>| |  
  
## <a name="see-also"></a><span data-ttu-id="cb9ff-154">参照</span><span class="sxs-lookup"><span data-stu-id="cb9ff-154">See Also</span></span>  
 <span data-ttu-id="cb9ff-155">[EDI 標準のサポート](../core/edi-standards-support.md) </span><span class="sxs-lookup"><span data-stu-id="cb9ff-155">[EDI Standards Support](../core/edi-standards-support.md) </span></span>  
 <span data-ttu-id="cb9ff-156">[EDI ドキュメント スキーマのサポート](../core/edi-document-schema-support.md) </span><span class="sxs-lookup"><span data-stu-id="cb9ff-156">[EDI Document Schema Support](../core/edi-document-schema-support.md) </span></span>  
 [<span data-ttu-id="cb9ff-157">EDI 文字セットのサポート</span><span class="sxs-lookup"><span data-stu-id="cb9ff-157">EDI Character Set Support</span></span>](../core/edi-character-set-support.md)