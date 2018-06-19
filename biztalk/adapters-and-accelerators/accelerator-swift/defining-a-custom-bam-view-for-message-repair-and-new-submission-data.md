---
title: Message Repair and 新しい送信データのカスタム BAM ビューの定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views
- Message Repair and New Submission, BAM views
ms.assetid: 76a6e78d-9b11-4b43-a500-a9d7666ee468
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88ec7506a299476dccb6ef9f9d0125768ea80b6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006819"
---
# <a name="defining-a-custom-bam-view-for-message-repair-and-new-submission-data"></a>Message Repair and 新しい送信データのカスタム BAM ビューを定義します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップでは、ビジネス アクティビティとビジネス ビューを定義する BAM 定義ファイルを提供します。 そのビューを使用する BAM 定義ファイルを展開することができますか、BAM 定義ファイルに追加できるカスタム ビューを作成することができます。  
  
 BAM 定義ファイルはで MrsrActivities.xml *\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\BAMTracking です。 メッセージ アクティビティと RepairView ビューを定義します。 MrsrActivities.xml を bm を使用して、展開の詳細について展開ユーティリティ、BizTalk Server ヘルプを参照してください。  
  
 ビジネス アクティビティ監視ビュー ウィザードで BAM ブックからカスタム ビューを作成します。 カスタム ビューの作成に関する詳細については、「BAM ビューを作成する」を参照してください[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server 情報ワーカーのヘルプ。  
  
 MrsrActivities.xml でメッセージ アクティビティには、カスタム ビューに追加することができますを次の項目が含まれています。  
  
> [!NOTE]
>  BAM では、期間が計算され、ときに 1 日 (14.4 分 =.01 日) の単位で測定されます。  
  
|アイテム|新しく使用する機能|アイテムの種類|  
|----------|---------|---------------|  
|移行先 BIC|メッセージの受信者の LT アドレス (SWIFT からのアプリケーション ヘッダー ブロック入力からのメッセージに SWIFT、またはメッセージの場合はブロック 1 の取得場所、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]機関先である)。<br /><br /> このデータが常に (アプリケーション ヘッダー入力先 LT SWIFTBound メッセージまたは SWIFT から受信したメッセージの基本的なヘッダー LT を使用して)。|ビジネス データ - Text|  
|[終了時刻]|日時 MRSRRepair オーケストレーションが (MRSR_Completed または MRSR_Failed)、メッセージの処理を完了するとします。<br /><br /> このデータと終了が完了したメッセージ MRSR ワークフロー、つまり、に対してのみ存在**BTS です。操作** == **A4SWIFT_MRSRCompleted**または**A4SWIFT_MRSRFailed**です。|ビジネス マイルス トーン|  
|リファレンス|このメッセージまたは送信側の機関; によって割り当てられたトランザクションの識別子の一意の参照フィールド 20 または 20C(SEME) から取得|ビジネス データ - Text|  
|メッセージの種類|FIN または GPA メッセージの種類。<br /><br /> このデータは常に存在 (アプリケーション ヘッダー入力またはアプリケーション ヘッダーを出力) します。|ビジネス データ - Text|  
|New Submission|新しいエントリ (Y) または別のシステムまたは SWIFT (N) から発信されたメッセージはこれ、かどうかを示すインジケーターです。<br /><br /> このデータは、作成機能を持つロールによって発信されたメッセージにのみ存在します。|ビジネス データ - Text|  
|[Priority]|SWIFT メッセージの優先順位 (N = normal、U = 緊急、S = システム)。<br /><br /> このデータは常に存在します。|ビジネス データ - Text|  
|受信時間|日付と時刻の MRSRRepair オーケストレーションが最後のメッセージを受信すると (– 前のステージからは、次のステージを参照してください)。<br /><br /> このデータは常に存在します。|ビジネス マイルス トーン|  
|送信者 BIC|メッセージの送信者の LT アドレス (SWIFT メッセージのブロック 1 から取得され、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]機関は、送信者または SWIFT からのメッセージをアプリケーション ヘッダーを出力から)。<br /><br /> このデータが常に (SWIFTBound メッセージ用の基本的なヘッダー LT アドレスまたは SWIFT から受信したメッセージをアプリケーション ヘッダーを出力から)。|ビジネス データ - Text|  
|時間を送信します。|日付と MRSRRepair オーケストレーション最後に送信されたとき、メッセージ MRSR サイト (現在のステージ) の時刻。<br /><br /> このデータは、メッセージは、オーケストレーションで処理しない限り、常に存在します。|ビジネス マイルス トーン|  
|Start Time|日付と MRSRRepair オーケストレーション最初に受信された時刻、メッセージ、新しい送信または (内部システムまたは SWIFT) インターフェイスからのメッセージとして。<br /><br /> このデータは常に存在します。|ビジネス マイルス トーン|  
|最後のステージ|ワークフロー (常にメッセージがここでは前に、の段階) で完了した最後の手順|ビジネス データ - Text|  
|[状態]|次の値をとります。<br /><br /> 完成した (正常終了した場合)<br />-リセットしての理由 (ワークフローのワークフローが再起動される場合は、リセット)<br />障害の発生し、(場合は、正常に完了しなかったメッセージが拒否されたか、タイムアウト) の理由します。<br /><br /> このデータは常に存在します。|ビジネス データ - Text|  
|Department|部門のポリシーに従って MRSRRepair オーケストレーションによって選択されている部門 (に依存する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]機関)|ビジネス データ - Text|  
|Username|前のステージに関連付けられているユーザーの名前 (上記の段階を参照してください)|ビジネス データ - Text|  
|現在のステージ|MRSRRepair オーケストレーションに (たとえば、受信トレイ) メッセージが配信ワークフロー ステップです。<br /><br /> このデータは、メッセージのメッセージの修復が完了しない限り存在します。|ビジネス データ - Text|