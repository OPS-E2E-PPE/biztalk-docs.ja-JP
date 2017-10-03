---
title: "ログ記録処理に関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07dba617358d6ad451c53eeb75dbe5d1986f9066
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-logging-process"></a>ログ記録処理について
重要なアプリケーションを処理するための監査、機密情報および通貨のデータを時間は、アプリケーションの重要な部分になります。 エンタープライズ レベルの管理性と可用性を有効にする[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]共有の次の実行時および管理のコンポーネントに依存しています。  
  
-   **ログ記録**: 収集およびルーティングするすべてのログ イベントで指定されたデータベースへの管理方法  
  
-   **イベントの監視とサービスのデバッグ**: ログ記録の動作を構成してシステム管理者およびその他の IT プロフェッショナル向けの情報を収集の調査/管理  
  
 拡張機能を監査[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、運用効率、セキュリティ、および HL7 規制に準拠するためのパフォーマンスを最適化することができます。  
  
## <a name="types-of-data"></a>データの種類  
 このトピックでは、ログ記録機能によって、このデータの保存場所を使用するログ データのさまざまな種類について説明します。  
  
-   構成データ: 構成データのログ記録は、構成データベース (BizTalk 管理データベースとも呼ばれます) に格納され、SQL 監査情報および監査データが含まれています ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ビューアーでは、集中化されたデータベース WMI) の場所。  
  
-   アーカイブ データ: SQL ログで、イベント ログ テーブルは、'ログ' のデータを格納します。  
  
## <a name="how-logging-works"></a>ログ記録のしくみ  
 このトピックでは、3 種類のログに記録されたデータを格納する 3 つの場所だけでなく、ソフトウェアのログ イベントについて説明します。  
  
|コンポーネント|用途|  
|---------------|-------------|  
|構成エディター|ログ データを保存する場所を指定します。 BTAHL7 は、次の任意の組み合わせへのログ記録をサポートしています。 イベント ビューアー、WMI、および SQL Server のログ記録します。|  
|イベント ブローカー|ログを受信するには、イベントは他のコンポーネントによって発生したし、構成データのログ記録を基にログを記録します。|  
|ログ記録 API|ログ記録のインターフェイスが BTAHL7 のすべてのアセンブリによって呼び出されます。|  
  
### <a name="types-of-logging"></a>ログの種類  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次の 3 つの種類のエラーをログに記録します。  
  
-   情報イベント、開始または停止されたサービスまたはイベントが失敗しました。  
  
-   警告イベントの重大でないエラーや警告など[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ログです。 たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データの検証に失敗したため、メッセージを中断します。  
  
-   コンポーネントで重大なエラーのエラー イベント。 たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサー エラーのため、メッセージを中断します。  
  
 システムにログオン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次の構成可能な場所にイベント。  
  
-   [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ビューアー  
  
-   WMI イベント  
  
-   集中化されたデータベース (SQL ログ データベース)  
  
 イベント ブローカーがすべて受信[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベントのログ記録し、構成情報に基づいて、適切な場所に送信します。  
  
### <a name="overview-of-features"></a>機能の概要  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ機能を提供します。  
  
-   すべてのエラー メッセージのログ記録のための統一された方法  
  
-   すべてのイベントの詳細を格納するための一元的なリポジトリ  
  
-   不連続の基幹業務アプリケーションへのログのメッセージ フローの一貫性のあるオブジェクト モデル  
  
-   ログとシステム管理者を関連付けるためのトレースの組み合わせでは、ドキュメントでエラーが記録されました  
  
## <a name="event-log-data"></a>イベント ログ データ  
 このトピックでは、形式と、イベント ログ データの内容について説明します。  
  
 次の表は、パートナーの通常のログに記録されたデータを示します。  
  
|data|Description|  
|----------|-----------------|  
|ログデータ|データのログ|  
|CategoryNumber|カテゴリの数|  
|EntryType|イベントの種類|  
|イベント Id|イベント ID|  
|MachineName|[コンピューター名]|  
|メッセージ|メッセージの詳細|  
|ソース|作成、更新、読み取り、削除、配置、またはデータのアーカイブ|  
|TimeGenerated|成功または失敗|  
|UserName|ユーザー名|  
|MsgGuid|メッセージの GUID|  
|SvcGuid|Service/ServiceGUID|  
|操作|操作の詳細|  
  
## <a name="see-also"></a>参照  
 [ログの構成](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)