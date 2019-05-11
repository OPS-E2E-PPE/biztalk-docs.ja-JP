---
title: アラートの頻度を変更する方法は、評価 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8ef990f851b9268e4cd6496b57a38318034534
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342448"
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a>警告を評価する頻度を変更する方法
これで、SQL Notification services ジェネレーター可能性がありますに対応できない既定の設定で展開すると、BAM イベント プロバイダーで発生するイベントの場合があります。 イベントを評価警告の Notification Services の adf.xml ファイルを変更して頻度 (クォンタム期間) を増やすことができます。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、この手順を実行する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]読み取りと一般には、プライマリ インポート データベースに書き込みアクセス許可を持つグループを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a>Notification Services ジェネレーターのクォンタム期間を変更するには  
  
1.  Notification Services コマンド プロンプトを開きます。 をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2005**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。  
  
2.  Notification Services の構成ファイルを取得します。 コマンド プロンプトで「: **cscript ProcessBamNSFiles.vbs--get config.xml adf.xml \<PimaryImport データベース サーバー\> \< PimaryImport データベース名\>** します。  
  
3.  変更または追加、 \<QuantumDuration\>の下の要素、 \<ApplicationExecutionSettings\>内のノード、adf.xml ファイル。 QuantumDuration 要素の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803)します。  
  
4.  コマンド プロンプトで「: **cscript ProcessBamNSFiles.vbs-更新 config.xml adf.xml \<PimaryImport データベース サーバー\> \< PimaryImport データベース名\>します。**  
  
## <a name="see-also"></a>参照  
 [Notification Services 構成ファイル用の BAM コマンド ライン スクリプト](../core/bam-command-line-script-for-notification-services-configuration-files.md)