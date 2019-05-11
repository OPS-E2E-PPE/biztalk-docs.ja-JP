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
# <a name="about-the-logging-process"></a>ログ処理の概要
重要なアプリケーションを処理するための監査、機密性の高いや通貨のデータを時間は、アプリケーションの重要な部分になります。 エンタープライズ レベルの管理性と可用性を Microsoft に有効にする[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]次の共有ランタイムと管理のコンポーネントに依存しています。  
  
- **ログ記録**: 指定されたデータベースに管理された方法でイベントを記録すべて収集およびルーティングするには  
  
- **イベントの監視とサービスのデバッグ**: ログ記録の動作を構成し、収集した情報システム管理者およびその他の IT プロフェッショナル向けの調査/管理するには  
  
  強化された機能の監査[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の運用効率、セキュリティ、および HL7 規制に準拠するためのパフォーマンスを最適化することができます。  
  
## <a name="types-of-data"></a>データの種類  
 このトピックでは、さまざまな種類のログ記録機能によって、このデータの保存場所を使用するログ データについて説明します。  
  
- 構成データ。構成データのログ記録は、構成データベース (BizTalk 管理データベースとも呼ばれます) に格納され、SQL 監査情報と監査データが含まれています ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ビューアーでは、集中管理されたデータベースの WMI) の場所。  
  
- アーカイブ データ:SQL ログのイベント ログ テーブルには、'ログ' のデータが格納されます。  
  
## <a name="how-logging-works"></a>ログ記録のしくみ  
 このトピックでは、3 種類のイベント ログに記録されたデータを格納する 3 つの場所と、ソフトウェアのログについて説明します。  
  
|コンポーネント|目的|  
|---------------|-------------|  
|構成エディター|ログ データを保存する場所を指定します。 BTAHL7 では、次の任意の組み合わせへのログ記録をサポートします。イベント ビューアー、WMI、および SQL Server のログ記録します。|  
|イベント ブローカー|ログを受信するには、イベントは、他のコンポーネントによって生成されると、構成データのログ記録に基づいたログインします。|  
|ロギング API|ログ記録のインターフェイスが BTAHL7 のすべてのアセンブリによって呼び出されます。|  
  
### <a name="types-of-logging"></a>ログの種類  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 次の 3 つの種類のエラーが記録されます。  
  
- 情報イベント、開始または停止されたサービスまたはイベントが失敗しました。  
  
- 警告イベントの重大でないエラーや警告など[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]イベント ログ。 たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データの検証に失敗したため、メッセージを中断します。  
  
- コンポーネントでの重大な障害のエラー イベント。 たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサー エラーのため、メッセージを中断します。  
  
  システムにログオン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次の構成可能な場所にイベント。  
  
- [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] イベント ビューアー  
  
- WMI イベント  
  
- 一元化されたデータベース (SQL ログ データベース)  
  
  すべてがイベント ブローカーが受信[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベントのログ記録、構成情報に基づいて、適切な場所に送信します。  
  
### <a name="overview-of-features"></a>機能の概要  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ機能を提供します。  
  
-   すべてのエラー メッセージをログ記録の統一された方法  
  
-   すべてのイベントの詳細を格納するリポジトリを集中管理  
  
-   ログ メッセージのフローに個別の基幹業務アプリケーションに一貫したオブジェクト モデル  
  
-   ログ記録とトレースをシステム管理者に関連付けるための組み合わせのドキュメントのエラーの記録  
  
## <a name="event-log-data"></a>イベント ログ データ  
 このトピックでは、イベント ログ データの内容と形式について説明します。  
  
 次の表は、パートナーの一般的なログに記録されたデータを示します。  
  
|data|説明|  
|----------|-----------------|  
|ログデータ|データのログ|  
|CategoryNumber|カテゴリの数|  
|EntryType|イベントの種類|  
|イベント Id|イベント ID|  
|MachineName|コンピューター名|  
|メッセージ|メッセージの詳細|  
|ソース|作成、更新、読み取り、削除、展開、またはデータのアーカイブ|  
|TimeGenerated|成功または失敗|  
|UserName|[ユーザー名]|  
|MsgGuid|メッセージ GUID|  
|SvcGuid|サービス GUID|  
|操作|操作の詳細|  
  
## <a name="see-also"></a>参照  
 [ログ記録の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)