---
title: Message Repair and New Submission データのカスタム BAM ビューの定義 |Microsoft Docs
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
ms.openlocfilehash: 490c1244b8ea63dda255220569f3ccee4e0f70c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007843"
---
# <a name="defining-a-custom-bam-view-for-message-repair-and-new-submission-data"></a>Message Repair and New Submission データのカスタム BAM ビューの定義
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] セットアップでは、ビジネス アクティビティとビジネス ビューを定義する BAM 定義ファイルを提供します。 そのビューを使用する BAM 定義ファイルをデプロイすることも、BAM 定義ファイルに追加できるカスタム ビューを作成することができます。  

 BAM 定義ファイルがで MrsrActivities.xml *\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\BAMTracking します。 メッセージ アクティビティおよび RepairView ビューを定義します。 MrsrActivities.xml を bm を使用して、展開の詳細について展開ユーティリティ、BizTalk Server のヘルプを参照してください。  

 ビジネス アクティビティ監視ビュー ウィザードで BAM ブックからカスタム ビューを作成します。 カスタム ビューの作成方法の詳細については、「を作成する BAM ビューを」MicrosoftBizTalk サーバー情報ワーカーのヘルプを参照してください。  

 MrsrActivities.xml メッセージ アクティビティには、カスタム ビューに追加することができます、次のものが含まれます。  

> [!NOTE]
>  BAM では、期間を計算して、ときに、1 日 (14.4 分 =.01 日) の単位で測定されます。  

|      アイテム       |                                                                                                                                                                                                                                  新しく使用する機能                                                                                                                                                                                                                                   |      アイテムの種類       |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| 移行先 BIC | メッセージの受信者の LT アドレス (SWIFT からのアプリケーション ヘッダー ブロックへの入力メッセージの SWIFT、またはメッセージのブロック 1 からの取得場所、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]教育機関は、変換先)。<br /><br /> このデータは、存在するは、(アプリケーション ヘッダー入力先 LT SWIFTBound メッセージ、または SWIFT から受信したメッセージの基本的なヘッダー LT を使用して) は常に。 | ビジネス データ - Text |
|    [終了時刻]     |                                                                            日付と時刻 MRSRRepair オーケストレーションが (MRSR_Completed または MRSR_Failed) メッセージの処理を完了するとします。<br /><br /> このデータは、つまり MRSR のワークフローを完了したメッセージが伴ってに対してのみ存在する**BTS します。操作** == **A4SWIFT_MRSRCompleted**または**A4SWIFT_MRSRFailed**します。                                                                             |  ビジネス マイルス トーン  |
|    リファレンス    |                                                                                                                                                                このメッセージまたは送信の教育機関; によって割り当てられたトランザクションの識別子の一意の参照20 のフィールドまたは 20C(SEME) から取得されます。                                                                                                                                                                | ビジネス データ - Text |
|  メッセージ型   |                                                                                                                                                                    FIN または GPA メッセージの種類。<br /><br /> このデータは常に存在 (ヘッダー入力のアプリケーションまたはアプリケーション ヘッダーを出力)。                                                                                                                                                                    | ビジネス データ - Text |
| New Submission  |                                                                                                                       新しいエントリ (Y) または別のシステムまたは SWIFT (N) から送信されたメッセージは、このかどうかを示すインジケーター。<br /><br /> このデータは、メッセージを作成する機能を持つロールで実行された場合にのみ存在します。                                                                                                                        | ビジネス データ - Text |
|    [Priority]     |                                                                                                                                                                            SWIFT メッセージの優先順位 (N = normal、U = 緊急、S = システム)。<br /><br /> このデータは、常に存在します。                                                                                                                                                                            | ビジネス データ - Text |
|  受信時刻  |                                                                                                                                                  日付と時刻の MRSRRepair オーケストレーションが最終メッセージを受信すると (– 前の段階から次を参照してください)。<br /><br /> このデータは、常に存在します。                                                                                                                                                   |  ビジネス マイルス トーン  |
|   送信者 BIC    |        メッセージの発信元の LT アドレス (SWIFT へのメッセージ ブロックの 1 から取得場所、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]教育機関は、送信者またはアプリケーション ヘッダーを SWIFT からのメッセージを出力から)。<br /><br /> このデータは、(SWIFTBound メッセージの場合の基本的なヘッダー LT アドレスかアプリケーション ヘッダーを SWIFT から受信したメッセージの出力を使用して) に存在しては常にします。        | ビジネス データ - Text |
|    送信時間    |                                                                                                                             日付と時刻と MRSRRepair オーケストレーションに送信された前回メッセージ MRSR サイト (現在の段階) 用です。<br /><br /> このデータは、メッセージが、オーケストレーションで処理しない限り、常に存在します。                                                                                                                             |  ビジネス マイルス トーン  |
|   Start Time    |                                                                                                                          日付と時刻と MRSRRepair オーケストレーション最初にメッセージを受信した新しい送信、または (内部システムまたは SWIFT) インターフェイスからのメッセージとして。<br /><br /> このデータは、常に存在します。                                                                                                                          |  ビジネス マイルス トーン  |
|   最後のステージ    |                                                                                                                                                                                       最後には、ワークフロー (常に、メッセージがここでは前に、のステージ) の手順が完了しました。                                                                                                                                                                                       | ビジネス データ - Text |
|     状態      |                                                                                               次の値をとります。<br /><br /> -完了 (正常終了した場合)<br />-をリセットし、(ワークフローのワークフローが再起動された場合のリセット) の理由<br />-失敗したため、(場合、正常に完了しなかったメッセージが拒否されましたがタイムアウト) の理由します。<br /><br /> このデータは、常に存在します。                                                                                                | ビジネス データ - Text |
|   Department    |                                                                                                                          部門ポリシーに従って MRSRRepair オーケストレーションによって選択した部門 (に依存する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]教育機関)                                                                                                                           | ビジネス データ - Text |
|    Username     |                                                                                                                                                                                               前のステージに関連付けられているユーザーの名前 (上記の段階を参照してください)                                                                                                                                                                                                | ビジネス データ - Text |
|  現在のステージ  |                                                                                                                                     MRSRRepair オーケストレーションに (たとえば、受信トレイ) メッセージが配信ワークフローの手順。<br /><br /> メッセージがメッセージの修復を完了していなければ、このデータは存在します。                                                                                                                                      | ビジネス データ - Text |

