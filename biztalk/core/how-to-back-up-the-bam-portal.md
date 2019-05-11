---
title: BAM ポータルをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbfa35fd3adc6fbbcba247fbc5c093a52c05f044
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387102"
---
# <a name="how-to-back-up-the-bam-portal"></a>BAM ポータルをバックアップする方法
ビジネス アクティビティ監視 (BAM) を使用している場合は、BizTalk server のバックアップの一部として、BAM ポータルをバックアップする必要があります。 BAM を使用していない場合は、この手順を省略できます。  
  
 バックアップ プロセスの特定の部分は、バックアップするインターネット インフォメーション サービス (IIS) のバージョンに応じて著しく異なります。 IIS 6.0 では、アプリケーション プールの構成と web サイトの構成を個別にバックアップして、パスワードを使用して、構成のバックアップ ファイルを暗号化することができます。  
  
 IIS 7.0 アプリケーション プールと web サイトの両方の構成設定を 1 つのファイルに保存する applicationHost.config します。ApplicationHost.config ファイルは暗号化されませんが、アカウントのパスワードは、存在する場合、ファイルに暗号化されます。 暗号化は、バックアップするには、コンピューターから証明書を使用して実行されます。 この構成は、元の 1 つ以外のコンピューターに復元できません。  
  
 IIS 7.0 マネージャーを使用して BAM ポータルの構成をバックアップすることはできません。使用する必要があります、 **Appcmd.exe**コマンド ライン ツール。 Appcmd の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497)します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a>BAM ポータル (IIS 7.0) をバックアップするには  
  
1.  **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。  
  
2.  実行 ダイアログ ボックスで、名前 ボックスで、以下を入力: `runas /user:` *computername*`\`*accountname* `cmd`、クリックして**OK**またはキーを押して**Enter**です。  
  
     *Accountname*ローカル コンピューターの administrators グループのメンバーである必要があります。  
  
3.  パスワードを入力メッセージが表示されたら、 *accountname*、キーを押します**Enter**です。  
  
4.  型`cd %windir%\system32\inetsrv`、キーを押します**Enter**です。  
  
5.  型`appcmd add backup “`*バックアップ名*`”`、キーを押します**Enter**です。  
  
     バックアップ名を入力する必要はありません。 かどうか設定されていないことが自動生成されます。 自動生成されたバックアップの名前の例としては"20090224T123302"にします。  
  
     既存の構成のバックアップの一覧を表示するには、次のように入力します。 `appcmd list backup`、キーを押しますと **」と入力**します。 ユーザーによって作成されたバックアップの保存、 **%windir%\system32\inetsrv\backup**ディレクトリ。 によって提供されるバックアップ オプションの一覧を表示する**appcmd.exe**、型`appcmd backup /?`、キーを押しますと **」と入力**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)   
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM ポータル](../core/bam-portal.md)