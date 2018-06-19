---
title: BAM ポータルをバックアップする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 27e7308e54505c795e35ffa2fbb2d287c1a49ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247122"
---
# <a name="how-to-back-up-the-bam-portal"></a>BAM ポータルをバックアップする方法
ビジネス アクティビティの監視 (BAM) を使用している場合は、BizTalk Server のバックアップ処理の一環として BAM ポータルをバックアップする必要があります。 BAM を使用していない場合は、この手順を省略できます。  
  
 バックアップ プロセスの一部は、バックアップ対象のインターネット インフォメーション サービス (IIS) のバージョンによって異なります。 IIS 6.0 では、アプリケーション プール構成と Web サイト構成を別々にバックアップでき、パスワードを使用して構成バックアップ ファイルを暗号化できます。  
  
 IIS 7.0 アプリケーション プールと web サイトの両方の構成設定を 1 つのファイルに保存する applicationHost.config です。ApplicationHost.config ファイルが暗号化されていないが、アカウントのパスワードは、存在する場合、ファイルで暗号化がします。 暗号化はバックアップ対象のコンピューターの証明書を使用して実行されます。 この構成は、元のコンピューター以外のコンピューターには復元できません。  
  
 IIS 7.0 マネージャーを使用して BAM ポータルの構成をバックアップすることはできません。使用する必要があります、 **Appcmd.exe**コマンド ライン ツールです。 Appcmd の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497)です。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a>BAM ポータル (IIS 7.0) をバックアップするには  
  
1.  **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。  
  
2.  実行 ダイアログ ボックスで、名前 ボックスで、以下を入力: `runas /user:` *computername*`\`*accountname* `cmd`、クリックして**OK**またはキーを押して**Enter**です。  
  
     *Accountname*ローカル コンピューターの administrators グループのメンバーである必要があります。  
  
3.  パスワードを入力メッセージが表示されたら、 *accountname*、キーを押します**Enter**です。  
  
4.  型`cd %windir%\system32\inetsrv`、キーを押します**Enter**です。  
  
5.  型`appcmd add backup “`*バックアップ名*`”`、キーを押します**Enter**です。  
  
     バックアップ名を入力する必要はありません。 設定しない場合は、自動的に生成されます。 たとえば、自動生成されたバックアップ名は "20090224T123302" になります。  
  
     既存の構成バックアップの一覧を表示するには、次のように入力します。 `appcmd list backup`、キーを押します**Enter**です。 ユーザーによって作成されたバックアップが保存される、 **%windir%\system32\inetsrv\backup**ディレクトリ。 によって指定されたバックアップ オプションの一覧を表示する**appcmd.exe**、型`appcmd backup /?`、キーを押します**Enter**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)   
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM ポータル](../core/bam-portal.md)