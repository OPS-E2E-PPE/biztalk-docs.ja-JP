---
title: ログ処理の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e12b1d3505da37294fa50e7f1570d6b8566664da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247501"
---
# <a name="about-the-logging-process"></a><span data-ttu-id="6cd77-102">ログ処理の概要</span><span class="sxs-lookup"><span data-stu-id="6cd77-102">About the Logging Process</span></span>
<span data-ttu-id="6cd77-103">重要なアプリケーションを処理するための監査、機密性の高いや通貨のデータを時間は、アプリケーションの重要な部分になります。</span><span class="sxs-lookup"><span data-stu-id="6cd77-103">Since your applications handle critical, time sensitive and monetary data, auditing becomes a critical part of the application.</span></span> <span data-ttu-id="6cd77-104">エンタープライズ レベルの管理性と可用性を Microsoft に有効にする[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]次の共有ランタイムと管理のコンポーネントに依存しています。</span><span class="sxs-lookup"><span data-stu-id="6cd77-104">To enable enterprise level manageability and availability, Microsoft [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] relies on the following shared run time and administrative components:</span></span>  
  
- <span data-ttu-id="6cd77-105">**ログ記録**: 指定されたデータベースに管理された方法でイベントを記録すべて収集およびルーティングするには</span><span class="sxs-lookup"><span data-stu-id="6cd77-105">**Logging**: to collect and route all log events in a managed way to a designated database</span></span>  
  
- <span data-ttu-id="6cd77-106">**イベントの監視とサービスのデバッグ**: ログ記録の動作を構成し、収集した情報システム管理者およびその他の IT プロフェッショナル向けの調査/管理するには</span><span class="sxs-lookup"><span data-stu-id="6cd77-106">**Event Monitoring and Service Debugging**: to configure logging behavior and to investigate/manage collected information for system administrators and other IT professionals</span></span>  
  
  <span data-ttu-id="6cd77-107">強化された機能の監査[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の運用効率、セキュリティ、および HL7 規制に準拠するためのパフォーマンスを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="6cd77-107">With the enhanced auditing features in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], you can optimize your operational efficiency, security, and performance to ensure compliance with HL7 regulations.</span></span>  
  
## <a name="types-of-data"></a><span data-ttu-id="6cd77-108">データの種類</span><span class="sxs-lookup"><span data-stu-id="6cd77-108">Types of Data</span></span>  
 <span data-ttu-id="6cd77-109">このトピックでは、さまざまな種類のログ記録機能によって、このデータの保存場所を使用するログ データについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-109">This topic describes different types of logging data used by the logging feature and where this data is stored:</span></span>  
  
- <span data-ttu-id="6cd77-110">構成データ。構成データのログ記録は、構成データベース (BizTalk 管理データベースとも呼ばれます) に格納され、SQL 監査情報と監査データが含まれています ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ビューアーでは、集中管理されたデータベースの WMI) の場所。</span><span class="sxs-lookup"><span data-stu-id="6cd77-110">Configuration data: Logging configuration data is stored in the Configuration database (also known as the BizTalk Management database) and includes SQL auditing information and audit data ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event viewer, centralized database WMI) location.</span></span>  
  
- <span data-ttu-id="6cd77-111">アーカイブ データ:SQL ログのイベント ログ テーブルには、'ログ' のデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6cd77-111">Archival data: The EventLog table in the SQL log stores the 'Logging' data.</span></span>  
  
## <a name="how-logging-works"></a><span data-ttu-id="6cd77-112">ログ記録のしくみ</span><span class="sxs-lookup"><span data-stu-id="6cd77-112">How Logging Works</span></span>  
 <span data-ttu-id="6cd77-113">このトピックでは、3 種類のイベント ログに記録されたデータを格納する 3 つの場所と、ソフトウェアのログについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-113">This topic describes the three types of events the software logs, as well as the three locations where you can store the logged data.</span></span>  
  
|<span data-ttu-id="6cd77-114">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6cd77-114">Component</span></span>|<span data-ttu-id="6cd77-115">目的</span><span class="sxs-lookup"><span data-stu-id="6cd77-115">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="6cd77-116">構成エディター</span><span class="sxs-lookup"><span data-stu-id="6cd77-116">Configuration Editor</span></span>|<span data-ttu-id="6cd77-117">ログ データを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-117">To specify where to save the log data.</span></span> <span data-ttu-id="6cd77-118">BTAHL7 では、次の任意の組み合わせへのログ記録をサポートします。イベント ビューアー、WMI、および SQL Server のログ記録します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-118">BTAHL7 supports logging to any combination of the following: Event Viewer, WMI, and SQL Server logging.</span></span>|  
|<span data-ttu-id="6cd77-119">イベント ブローカー</span><span class="sxs-lookup"><span data-stu-id="6cd77-119">Event Broker</span></span>|<span data-ttu-id="6cd77-120">ログを受信するには、イベントは、他のコンポーネントによって生成されると、構成データのログ記録に基づいたログインします。</span><span class="sxs-lookup"><span data-stu-id="6cd77-120">To receive log events raised by other components and log them based on logging configuration data.</span></span>|  
|<span data-ttu-id="6cd77-121">ロギング API</span><span class="sxs-lookup"><span data-stu-id="6cd77-121">Logging API</span></span>|<span data-ttu-id="6cd77-122">ログ記録のインターフェイスが BTAHL7 のすべてのアセンブリによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6cd77-122">Logging interface called by all BTAHL7 assemblies.</span></span>|  
  
### <a name="types-of-logging"></a><span data-ttu-id="6cd77-123">ログの種類</span><span class="sxs-lookup"><span data-stu-id="6cd77-123">Types of Logging</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="6cd77-124">次の 3 つの種類のエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="6cd77-124">logs three types of errors:</span></span>  
  
- <span data-ttu-id="6cd77-125">情報イベント、開始または停止されたサービスまたはイベントが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6cd77-125">Informational events, such a service started or stopped or an event failed.</span></span>  
  
- <span data-ttu-id="6cd77-126">警告イベントの重大でないエラーや警告など[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ログ。</span><span class="sxs-lookup"><span data-stu-id="6cd77-126">Warning events such as non-critical errors and warnings in [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event logs.</span></span> <span data-ttu-id="6cd77-127">たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データの検証に失敗したため、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-127">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because data validation failed.</span></span>  
  
- <span data-ttu-id="6cd77-128">コンポーネントでの重大な障害のエラー イベント。</span><span class="sxs-lookup"><span data-stu-id="6cd77-128">Error events for critical failures in a component.</span></span> <span data-ttu-id="6cd77-129">たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサー エラーのため、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-129">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because of parser failures.</span></span>  
  
  <span data-ttu-id="6cd77-130">システムにログオン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次の構成可能な場所にイベント。</span><span class="sxs-lookup"><span data-stu-id="6cd77-130">The system can log [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] events into following configurable locations:</span></span>  
  
- [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] <span data-ttu-id="6cd77-131">イベント ビューアー</span><span class="sxs-lookup"><span data-stu-id="6cd77-131">Event viewer</span></span>  
  
- <span data-ttu-id="6cd77-132">WMI イベント</span><span class="sxs-lookup"><span data-stu-id="6cd77-132">WMI events</span></span>  
  
- <span data-ttu-id="6cd77-133">一元化されたデータベース (SQL ログ データベース)</span><span class="sxs-lookup"><span data-stu-id="6cd77-133">Centralized database (SQL logging database)</span></span>  
  
  <span data-ttu-id="6cd77-134">すべてがイベント ブローカーが受信[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベントのログ記録、構成情報に基づいて、適切な場所に送信します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-134">An event broker receives all [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging events and, based on the configuration information, sends them to the appropriate location.</span></span>  
  
### <a name="overview-of-features"></a><span data-ttu-id="6cd77-135">機能の概要</span><span class="sxs-lookup"><span data-stu-id="6cd77-135">Overview of Features</span></span>  
 <span data-ttu-id="6cd77-136">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-136">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging feature provides:</span></span>  
  
-   <span data-ttu-id="6cd77-137">すべてのエラー メッセージをログ記録の統一された方法</span><span class="sxs-lookup"><span data-stu-id="6cd77-137">A unified way of logging all the error messages</span></span>  
  
-   <span data-ttu-id="6cd77-138">すべてのイベントの詳細を格納するリポジトリを集中管理</span><span class="sxs-lookup"><span data-stu-id="6cd77-138">A centralized repository for storing all event details</span></span>  
  
-   <span data-ttu-id="6cd77-139">ログ メッセージのフローに個別の基幹業務アプリケーションに一貫したオブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="6cd77-139">A consistent object model for logging messages flowing to discrete line-of-business applications</span></span>  
  
-   <span data-ttu-id="6cd77-140">ログ記録とトレースをシステム管理者に関連付けるための組み合わせのドキュメントのエラーの記録</span><span class="sxs-lookup"><span data-stu-id="6cd77-140">A combination of logging and tracing to help system administrators correlate logged errors with documents</span></span>  
  
## <a name="event-log-data"></a><span data-ttu-id="6cd77-141">イベント ログ データ</span><span class="sxs-lookup"><span data-stu-id="6cd77-141">Event Log Data</span></span>  
 <span data-ttu-id="6cd77-142">このトピックでは、イベント ログ データの内容と形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-142">This topic describes the format and content of the event log data.</span></span>  
  
 <span data-ttu-id="6cd77-143">次の表は、パートナーの一般的なログに記録されたデータを示します。</span><span class="sxs-lookup"><span data-stu-id="6cd77-143">The following table shows typical logged data for partners.</span></span>  
  
|<span data-ttu-id="6cd77-144">data</span><span class="sxs-lookup"><span data-stu-id="6cd77-144">Data</span></span>|<span data-ttu-id="6cd77-145">説明</span><span class="sxs-lookup"><span data-stu-id="6cd77-145">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="6cd77-146">ログデータ</span><span class="sxs-lookup"><span data-stu-id="6cd77-146">LogData</span></span>|<span data-ttu-id="6cd77-147">データのログ</span><span class="sxs-lookup"><span data-stu-id="6cd77-147">Data log</span></span>|  
|<span data-ttu-id="6cd77-148">CategoryNumber</span><span class="sxs-lookup"><span data-stu-id="6cd77-148">CategoryNumber</span></span>|<span data-ttu-id="6cd77-149">カテゴリの数</span><span class="sxs-lookup"><span data-stu-id="6cd77-149">Category number</span></span>|  
|<span data-ttu-id="6cd77-150">EntryType</span><span class="sxs-lookup"><span data-stu-id="6cd77-150">EntryType</span></span>|<span data-ttu-id="6cd77-151">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="6cd77-151">Type of the event</span></span>|  
|<span data-ttu-id="6cd77-152">イベント Id</span><span class="sxs-lookup"><span data-stu-id="6cd77-152">EventId</span></span>|<span data-ttu-id="6cd77-153">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6cd77-153">Event ID</span></span>|  
|<span data-ttu-id="6cd77-154">MachineName</span><span class="sxs-lookup"><span data-stu-id="6cd77-154">MachineName</span></span>|<span data-ttu-id="6cd77-155">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="6cd77-155">Computer name</span></span>|  
|<span data-ttu-id="6cd77-156">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6cd77-156">Message</span></span>|<span data-ttu-id="6cd77-157">メッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="6cd77-157">Message detail</span></span>|  
|<span data-ttu-id="6cd77-158">ソース</span><span class="sxs-lookup"><span data-stu-id="6cd77-158">Source</span></span>|<span data-ttu-id="6cd77-159">作成、更新、読み取り、削除、展開、またはデータのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="6cd77-159">Creating, updating, reading, deleting, deploying, or archiving data</span></span>|  
|<span data-ttu-id="6cd77-160">TimeGenerated</span><span class="sxs-lookup"><span data-stu-id="6cd77-160">TimeGenerated</span></span>|<span data-ttu-id="6cd77-161">成功または失敗</span><span class="sxs-lookup"><span data-stu-id="6cd77-161">Success or Failure</span></span>|  
|<span data-ttu-id="6cd77-162">UserName</span><span class="sxs-lookup"><span data-stu-id="6cd77-162">UserName</span></span>|<span data-ttu-id="6cd77-163">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="6cd77-163">User name</span></span>|  
|<span data-ttu-id="6cd77-164">MsgGuid</span><span class="sxs-lookup"><span data-stu-id="6cd77-164">MsgGuid</span></span>|<span data-ttu-id="6cd77-165">メッセージ GUID</span><span class="sxs-lookup"><span data-stu-id="6cd77-165">Message GUID</span></span>|  
|<span data-ttu-id="6cd77-166">SvcGuid</span><span class="sxs-lookup"><span data-stu-id="6cd77-166">SvcGuid</span></span>|<span data-ttu-id="6cd77-167">サービス GUID</span><span class="sxs-lookup"><span data-stu-id="6cd77-167">Service GUID</span></span>|  
|<span data-ttu-id="6cd77-168">操作</span><span class="sxs-lookup"><span data-stu-id="6cd77-168">Operation</span></span>|<span data-ttu-id="6cd77-169">操作の詳細</span><span class="sxs-lookup"><span data-stu-id="6cd77-169">Operation detail</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cd77-170">参照</span><span class="sxs-lookup"><span data-stu-id="6cd77-170">See Also</span></span>  
 [<span data-ttu-id="6cd77-171">ログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="6cd77-171">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)