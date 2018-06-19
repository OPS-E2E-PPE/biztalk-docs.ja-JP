---
title: サービス構成ファイルの通知用の BAM コマンド ライン スクリプト |Microsoft ドキュメント
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
ms.openlocfilehash: b22607193ed7c345388a6435e2d58c16b8986370
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965800"
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a>Notification Services 構成ファイル用の BAM コマンド ライン スクリプト
管理者は、ProcessBamNSFiles.vbs スクリプトを使用して、BAM 警告の SQL Server Notification Services の動作をカスタマイズできます。 このスクリプトを使用して、Notification Services のアプリケーション定義ファイル (ADF) や Notification Services の構成ファイルを取得できます。 これらのファイルに変更を加えた後、スクリプトを使って変更内容を適用できます。  
  
 スクリプトは、通常のコマンド プロンプトからではなく、Notification Services のコマンド プロンプトから実行します。 通常のコマンド プロンプトからスクリプトを実行すると、スクリプトが適切に実行されません。 スクリプトの実行時には、すべてのパラメーターを指定する必要があります。  
  
## <a name="get-command"></a>Get コマンド  
 **使用方法**  
  
 **cscript ProcessBamNSFiles-取得\<構成ファイルのパス\> \<ADF ファイルのパス\>\<プライマリ インポート サーバー\> \<プライマリ インポート データベース  \>**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|構成ファイルのパス|構成ファイルの保存先の名前と場所を指定します。|  
|ADF ファイルのパス|ADF ファイルの保存先の名前と場所を指定します。|  
|プライマリ インポート サーバー|BAM プライマリ インポート データベースが格納されているコンピューターの名前です。|  
|プライマリ インポート データベース|BAM プライマリ インポート データベースの名前です。|  
  
 BAM プライマリ インポート データベースから Notification Services の構成ファイルおよびアプリケーション定義ファイルを取得し、それらを指定されたパスに保存します。  
  
## <a name="update-command"></a>Update コマンド  
 **使用方法**  
  
 **cscript ProcessBamNSFiles-更新\<configfilepath\> \<構成ファイルのパス\>\<primaryimport サーバー\> \<プライマリ インポート データベース  \>**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|構成ファイルのパス|最新の Notification Services 構成ファイルの名前と場所を指定します。|  
|ADF ファイルのパス|最新の ADF ファイルの名前と場所を指定します。|  
|プライマリ インポート サーバー|BAM プライマリ インポート データベースが格納されているコンピューターの名前です。|  
|プライマリ インポート データベース|BAM プライマリ インポート データベースの名前です。|  
  
 Notification Services を呼び出し、指定されたファイルの情報で設定を更新します。 構成ファイルと ADF ファイルは、BAM プライマリ インポート データベースに格納されます。  
  
## <a name="see-also"></a>参照  
 [BAM コマンド ライン ツール](../core/bam-command-line-tools.md)