---
title: 通知用の BAM コマンド ライン スクリプト サービス構成ファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf28ea2c1ff0defd7696b548ff86bc050259925d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528716"
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a>サービス構成ファイルの通知用の BAM コマンド ライン スクリプト
管理者は、ProcessBamNSFiles.vbs スクリプトを使用して、BAM 警告用 SQL Server Notification Services の動作をカスタマイズします。 Notification Services application 定義ファイル (ADF) と Notification Services 構成ファイルを取得するのにスクリプトを使用することができます。 これらのファイルを変更して、スクリプトを使用して、変更を適用します。  
  
 通常コマンド プロンプトではなく、Notification Services コマンド プロンプトからスクリプトを実行するとします。 一般的なコマンド プロンプトからスクリプトを実行すると、正しく実行するスクリプトが。 スクリプトを実行している場合は、すべてのパラメーターは必須です。  
  
## <a name="get-command"></a>Get コマンド  
 **使用方法**  
  
 **cscript ProcessBamNSFiles-取得\<構成ファイルのパス\> \<ADF ファイルのパス\>\<プライマリ インポート サーバー\> \<プライマリ インポート データベース  \>**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|構成ファイルのパス|構成ファイルを格納する場所と名前を指定します。|  
|ADF ファイルのパス|ADF ファイルを格納する場所と名前を指定します。|  
|プライマリ インポート サーバー|BAM プライマリ インポート データベースが格納されているコンピューターの名前。|  
|プライマリ インポート データベース|BAM プライマリ インポート データベースの名前。|  
  
 指定したパスを取得、Notification Services の構成およびアプリケーション定義ファイルを BAM プライマリ インポート データベースからとするために保存します。  
  
## <a name="update-command"></a>Update コマンド  
 **使用方法**  
  
 **cscript ProcessBamNSFiles-Update \<configfilepath\> \<構成\>\<primaryimport server\> \<プライマリ インポート db  \>**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|構成ファイルのパス|Notification Services の構成情報を更新する元の場所と名前を指定します。|  
|ADF ファイルのパス|ADF の情報を更新する元の場所と名前を指定します。|  
|プライマリ インポート サーバー|BAM プライマリ インポート データベースが格納されているコンピューターの名前。|  
|プライマリ インポート データベース|BAM プライマリ インポート データベースの名前。|  
  
 通知サービスを呼び出すし、指定されたファイルの情報と設定を更新します。 構成ファイルと ADF ファイルは、BAM プライマリ インポート データベースに格納されます。  
  
## <a name="see-also"></a>参照  
 [BAM コマンド ライン ツール](../core/bam-command-line-tools.md)