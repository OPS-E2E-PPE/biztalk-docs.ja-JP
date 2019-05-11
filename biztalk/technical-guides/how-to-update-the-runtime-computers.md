---
title: ランタイム コンピューターを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d67497e3c462194e2306cf7ada0764943975cbb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395880"
---
# <a name="how-to-update-the-runtime-computers"></a>ランタイム コンピューターを更新する方法
送信先システム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターで構成されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境で実行されている運用環境の BizTalk グループの一部として構成します。 各設定を更新する必要があります、ディザスター リカバリー環境で運用環境の BizTalk グループが復元されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターのことが、ディザスター リカバリーを指すように[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元されたに接続しようとしたときにインスタンス運用環境の BizTalk グループ。 送信先システムで BizTalk グループが復元された後に、次の手順を使用して更新、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a>BizTalk Server ランタイム コンピューターを更新するには  
  
1. すべての 32 ビット BizTalk server 上のディレクトリに BizTalk Server\Schema\Restore \Program Files\Microsoft またはすべて 64 ビットの BizTalk では、\Program Files (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore ディレクトリには、編集した SampleUpdateInfo.xml ファイルをコピーします。送信先システムのサーバー。  
  
2. 各 BizTalk server では、コマンド プロンプトを開きます。 をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   > [!NOTE]  
   >  64 ビット コンピューターでは、64 ビット コマンド プロンプトを開く必要があります。  
  
3. コマンド プロンプトで、または (64 ビットのコンピューター) 上の \Program Files (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore \Program Files\Microsoft BizTalk Server\Schema\Restore (32 ビット コンピューター) に移動し、このコマンドを入力します。  
  
   ```  
   cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
   ```  
  
4. 有効にして、送信先システムですべての BizTalk ホスト インスタンスと、BizTalk server 上の他のすべての BizTalk サービスを再起動します。  
  
5. 送信先システムで、各 BizTalk サーバーで WMI を再起動します。 をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリックします**OK**。 **サービス**MMC スナップインで、右クリックして**Windows Management Instrumentation**選択**再起動**します。  
  
6. 各 BizTalk サーバーで開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**BizTalk グループ**、し、**削除**。  
  
7. 右クリック**BizTalk Server 2010 管理**、**既存グループへの接続**、SQL Server データベース インスタンスを選択し、データベース名の BizTalk 管理データベースに対応します。をクリックし、BizTalk グループ**OK**します。  
  
   > [!NOTE]
   >  更新した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターの場合は、する必要がありますも更新、 **SSO サーバー名**に表示される、**グループ プロパティ**ダイアログ ボックスで、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 更新する、 **SSO サーバー名**、起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理 を右クリックし、 **BizTalk グループ**ノードと選択**プロパティ**を表示する、**全般**のタブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 次に、 **SSO サーバー名**] ボックスに、アダプターの構成情報にアクセスして [このコンピューターが使用するエンタープライズ シングル サインオン サーバーの名前を入力**OK**します。 これは、SSO データベースへの接続に使用する SSO サーバーの名前です。  
  
8. 各 BizTalk ランタイム サーバーで、次の Windows サービスを再起動します。  
  
   -   エンタープライズ SSO サービス  
  
   -   ルール エンジン更新サービス  
  
   -   BizTalk ホスト インスタンス  
  
## <a name="see-also"></a>参照  
 [ランタイム コンピューターの回復](../technical-guides/recovering-the-runtime-computers.md)