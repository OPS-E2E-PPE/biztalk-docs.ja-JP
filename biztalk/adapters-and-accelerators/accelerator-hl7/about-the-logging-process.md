---
title: ログ記録処理に関する |Microsoft ドキュメント
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
ms.openlocfilehash: 07dba617358d6ad451c53eeb75dbe5d1986f9066
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204722"
---
# <a name="about-the-logging-process"></a><span data-ttu-id="7b4bf-102">ログ記録処理について</span><span class="sxs-lookup"><span data-stu-id="7b4bf-102">About the Logging Process</span></span>
<span data-ttu-id="7b4bf-103">重要なアプリケーションを処理するための監査、機密情報および通貨のデータを時間は、アプリケーションの重要な部分になります。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-103">Since your applications handle critical, time sensitive and monetary data, auditing becomes a critical part of the application.</span></span> <span data-ttu-id="7b4bf-104">エンタープライズ レベルの管理性と可用性を有効にする[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]共有の次の実行時および管理のコンポーネントに依存しています。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-104">To enable enterprise level manageability and availability, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] relies on the following shared run time and administrative components:</span></span>  
  
-   <span data-ttu-id="7b4bf-105">**ログ記録**: 収集およびルーティングするすべてのログ イベントで指定されたデータベースへの管理方法</span><span class="sxs-lookup"><span data-stu-id="7b4bf-105">**Logging**: to collect and route all log events in a managed way to a designated database</span></span>  
  
-   <span data-ttu-id="7b4bf-106">**イベントの監視とサービスのデバッグ**: ログ記録の動作を構成してシステム管理者およびその他の IT プロフェッショナル向けの情報を収集の調査/管理</span><span class="sxs-lookup"><span data-stu-id="7b4bf-106">**Event Monitoring and Service Debugging**: to configure logging behavior and to investigate/manage collected information for system administrators and other IT professionals</span></span>  
  
 <span data-ttu-id="7b4bf-107">拡張機能を監査[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、運用効率、セキュリティ、および HL7 規制に準拠するためのパフォーマンスを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-107">With the enhanced auditing features in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], you can optimize your operational efficiency, security, and performance to ensure compliance with HL7 regulations.</span></span>  
  
## <a name="types-of-data"></a><span data-ttu-id="7b4bf-108">データの種類</span><span class="sxs-lookup"><span data-stu-id="7b4bf-108">Types of Data</span></span>  
 <span data-ttu-id="7b4bf-109">このトピックでは、ログ記録機能によって、このデータの保存場所を使用するログ データのさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-109">This topic describes different types of logging data used by the logging feature and where this data is stored:</span></span>  
  
-   <span data-ttu-id="7b4bf-110">構成データ: 構成データのログ記録は、構成データベース (BizTalk 管理データベースとも呼ばれます) に格納され、SQL 監査情報および監査データが含まれています ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ビューアーでは、集中化されたデータベース WMI) の場所。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-110">Configuration data: Logging configuration data is stored in the Configuration database (also known as the BizTalk Management database) and includes SQL auditing information and audit data ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event viewer, centralized database WMI) location.</span></span>  
  
-   <span data-ttu-id="7b4bf-111">アーカイブ データ: SQL ログで、イベント ログ テーブルは、'ログ' のデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-111">Archival data: The EventLog table in the SQL log stores the 'Logging' data.</span></span>  
  
## <a name="how-logging-works"></a><span data-ttu-id="7b4bf-112">ログ記録のしくみ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-112">How Logging Works</span></span>  
 <span data-ttu-id="7b4bf-113">このトピックでは、3 種類のログに記録されたデータを格納する 3 つの場所だけでなく、ソフトウェアのログ イベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-113">This topic describes the three types of events the software logs, as well as the three locations where you can store the logged data.</span></span>  
  
|<span data-ttu-id="7b4bf-114">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7b4bf-114">Component</span></span>|<span data-ttu-id="7b4bf-115">用途</span><span class="sxs-lookup"><span data-stu-id="7b4bf-115">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="7b4bf-116">構成エディター</span><span class="sxs-lookup"><span data-stu-id="7b4bf-116">Configuration Editor</span></span>|<span data-ttu-id="7b4bf-117">ログ データを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-117">To specify where to save the log data.</span></span> <span data-ttu-id="7b4bf-118">BTAHL7 は、次の任意の組み合わせへのログ記録をサポートしています。 イベント ビューアー、WMI、および SQL Server のログ記録します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-118">BTAHL7 supports logging to any combination of the following: Event Viewer, WMI, and SQL Server logging.</span></span>|  
|<span data-ttu-id="7b4bf-119">イベント ブローカー</span><span class="sxs-lookup"><span data-stu-id="7b4bf-119">Event Broker</span></span>|<span data-ttu-id="7b4bf-120">ログを受信するには、イベントは他のコンポーネントによって発生したし、構成データのログ記録を基にログを記録します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-120">To receive log events raised by other components and log them based on logging configuration data.</span></span>|  
|<span data-ttu-id="7b4bf-121">ログ記録 API</span><span class="sxs-lookup"><span data-stu-id="7b4bf-121">Logging API</span></span>|<span data-ttu-id="7b4bf-122">ログ記録のインターフェイスが BTAHL7 のすべてのアセンブリによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-122">Logging interface called by all BTAHL7 assemblies.</span></span>|  
  
### <a name="types-of-logging"></a><span data-ttu-id="7b4bf-123">ログの種類</span><span class="sxs-lookup"><span data-stu-id="7b4bf-123">Types of Logging</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="7b4bf-124">次の 3 つの種類のエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-124"> logs three types of errors:</span></span>  
  
-   <span data-ttu-id="7b4bf-125">情報イベント、開始または停止されたサービスまたはイベントが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-125">Informational events, such a service started or stopped or an event failed.</span></span>  
  
-   <span data-ttu-id="7b4bf-126">警告イベントの重大でないエラーや警告など[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ログです。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-126">Warning events such as non-critical errors and warnings in [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event logs.</span></span> <span data-ttu-id="7b4bf-127">たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データの検証に失敗したため、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-127">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because data validation failed.</span></span>  
  
-   <span data-ttu-id="7b4bf-128">コンポーネントで重大なエラーのエラー イベント。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-128">Error events for critical failures in a component.</span></span> <span data-ttu-id="7b4bf-129">たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサー エラーのため、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-129">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because of parser failures.</span></span>  
  
 <span data-ttu-id="7b4bf-130">システムにログオン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次の構成可能な場所にイベント。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-130">The system can log [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] events into following configurable locations:</span></span>  
  
-   [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]<span data-ttu-id="7b4bf-131">イベント ビューアー</span><span class="sxs-lookup"><span data-stu-id="7b4bf-131"> Event viewer</span></span>  
  
-   <span data-ttu-id="7b4bf-132">WMI イベント</span><span class="sxs-lookup"><span data-stu-id="7b4bf-132">WMI events</span></span>  
  
-   <span data-ttu-id="7b4bf-133">集中化されたデータベース (SQL ログ データベース)</span><span class="sxs-lookup"><span data-stu-id="7b4bf-133">Centralized database (SQL logging database)</span></span>  
  
 <span data-ttu-id="7b4bf-134">イベント ブローカーがすべて受信[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベントのログ記録し、構成情報に基づいて、適切な場所に送信します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-134">An event broker receives all [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging events and, based on the configuration information, sends them to the appropriate location.</span></span>  
  
### <a name="overview-of-features"></a><span data-ttu-id="7b4bf-135">機能の概要</span><span class="sxs-lookup"><span data-stu-id="7b4bf-135">Overview of Features</span></span>  
 <span data-ttu-id="7b4bf-136">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-136">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging feature provides:</span></span>  
  
-   <span data-ttu-id="7b4bf-137">すべてのエラー メッセージのログ記録のための統一された方法</span><span class="sxs-lookup"><span data-stu-id="7b4bf-137">A unified way of logging all the error messages</span></span>  
  
-   <span data-ttu-id="7b4bf-138">すべてのイベントの詳細を格納するための一元的なリポジトリ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-138">A centralized repository for storing all event details</span></span>  
  
-   <span data-ttu-id="7b4bf-139">不連続の基幹業務アプリケーションへのログのメッセージ フローの一貫性のあるオブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="7b4bf-139">A consistent object model for logging messages flowing to discrete line-of-business applications</span></span>  
  
-   <span data-ttu-id="7b4bf-140">ログとシステム管理者を関連付けるためのトレースの組み合わせでは、ドキュメントでエラーが記録されました</span><span class="sxs-lookup"><span data-stu-id="7b4bf-140">A combination of logging and tracing to help system administrators correlate logged errors with documents</span></span>  
  
## <a name="event-log-data"></a><span data-ttu-id="7b4bf-141">イベント ログ データ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-141">Event Log Data</span></span>  
 <span data-ttu-id="7b4bf-142">このトピックでは、形式と、イベント ログ データの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-142">This topic describes the format and content of the event log data.</span></span>  
  
 <span data-ttu-id="7b4bf-143">次の表は、パートナーの通常のログに記録されたデータを示します。</span><span class="sxs-lookup"><span data-stu-id="7b4bf-143">The following table shows typical logged data for partners.</span></span>  
  
|<span data-ttu-id="7b4bf-144">data</span><span class="sxs-lookup"><span data-stu-id="7b4bf-144">Data</span></span>|<span data-ttu-id="7b4bf-145">Description</span><span class="sxs-lookup"><span data-stu-id="7b4bf-145">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7b4bf-146">ログデータ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-146">LogData</span></span>|<span data-ttu-id="7b4bf-147">データのログ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-147">Data log</span></span>|  
|<span data-ttu-id="7b4bf-148">CategoryNumber</span><span class="sxs-lookup"><span data-stu-id="7b4bf-148">CategoryNumber</span></span>|<span data-ttu-id="7b4bf-149">カテゴリの数</span><span class="sxs-lookup"><span data-stu-id="7b4bf-149">Category number</span></span>|  
|<span data-ttu-id="7b4bf-150">EntryType</span><span class="sxs-lookup"><span data-stu-id="7b4bf-150">EntryType</span></span>|<span data-ttu-id="7b4bf-151">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="7b4bf-151">Type of the event</span></span>|  
|<span data-ttu-id="7b4bf-152">イベント Id</span><span class="sxs-lookup"><span data-stu-id="7b4bf-152">EventId</span></span>|<span data-ttu-id="7b4bf-153">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7b4bf-153">Event ID</span></span>|  
|<span data-ttu-id="7b4bf-154">MachineName</span><span class="sxs-lookup"><span data-stu-id="7b4bf-154">MachineName</span></span>|<span data-ttu-id="7b4bf-155">[コンピューター名]</span><span class="sxs-lookup"><span data-stu-id="7b4bf-155">Computer name</span></span>|  
|<span data-ttu-id="7b4bf-156">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-156">Message</span></span>|<span data-ttu-id="7b4bf-157">メッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="7b4bf-157">Message detail</span></span>|  
|<span data-ttu-id="7b4bf-158">ソース</span><span class="sxs-lookup"><span data-stu-id="7b4bf-158">Source</span></span>|<span data-ttu-id="7b4bf-159">作成、更新、読み取り、削除、配置、またはデータのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="7b4bf-159">Creating, updating, reading, deleting, deploying, or archiving data</span></span>|  
|<span data-ttu-id="7b4bf-160">TimeGenerated</span><span class="sxs-lookup"><span data-stu-id="7b4bf-160">TimeGenerated</span></span>|<span data-ttu-id="7b4bf-161">成功または失敗</span><span class="sxs-lookup"><span data-stu-id="7b4bf-161">Success or Failure</span></span>|  
|<span data-ttu-id="7b4bf-162">UserName</span><span class="sxs-lookup"><span data-stu-id="7b4bf-162">UserName</span></span>|<span data-ttu-id="7b4bf-163">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="7b4bf-163">User name</span></span>|  
|<span data-ttu-id="7b4bf-164">MsgGuid</span><span class="sxs-lookup"><span data-stu-id="7b4bf-164">MsgGuid</span></span>|<span data-ttu-id="7b4bf-165">メッセージの GUID</span><span class="sxs-lookup"><span data-stu-id="7b4bf-165">Message GUID</span></span>|  
|<span data-ttu-id="7b4bf-166">SvcGuid</span><span class="sxs-lookup"><span data-stu-id="7b4bf-166">SvcGuid</span></span>|<span data-ttu-id="7b4bf-167">Service/ServiceGUID</span><span class="sxs-lookup"><span data-stu-id="7b4bf-167">Service GUID</span></span>|  
|<span data-ttu-id="7b4bf-168">操作</span><span class="sxs-lookup"><span data-stu-id="7b4bf-168">Operation</span></span>|<span data-ttu-id="7b4bf-169">操作の詳細</span><span class="sxs-lookup"><span data-stu-id="7b4bf-169">Operation detail</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b4bf-170">参照</span><span class="sxs-lookup"><span data-stu-id="7b4bf-170">See Also</span></span>  
 [<span data-ttu-id="7b4bf-171">ログの構成</span><span class="sxs-lookup"><span data-stu-id="7b4bf-171">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)