---
title: BizTalk Server の証明書をインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70a89595-8828-4872-b78b-77e9b0b048b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7133134ddd37562ec30112549bb1a4ac16149b03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969803"
---
# <a name="how-to-install-certificates-for-biztalk-server"></a>BizTalk Server の証明書をインストールする方法
データ転送をセキュリティで保護する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、適切な証明書を適切な証明書ストアに追加し、適切な BizTalk アイテム、証明書を関連付ける必要があります。 このトピックでは、適切なストアで適切な証明書をインストールする方法と、ローカル コンピューターと現在のユーザーの証明書ストアの証明書管理コンソール インターフェイスを表示する方法について説明します。  

 次の表に示すように証明書は、サインインのヘルプの署名の検証、暗号化、およびメッセージの解読に使用されます。  

|証明書の使用|証明書の種類|証明書ストア|  
|-----------------------|----------------------|-----------------------|  
|署名 (送信)|固有の秘密キー (.pfx)|現在のユーザー\\<br />各ホスト インスタンス サービス アカウントとして MIME/SMIME エンコーダ パイプラインをホストする各 BizTalk サーバーの個人用ストア|  
|署名の検証 (受信)|取引先の公開キー (.cer)|各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダ パイプラインをホストする各 BizTalk サーバーの Local computer\Other People ストア|  
|暗号化 (送信)|取引先の公開キー (.cer)|MIME/SMIME エンコーダ パイプラインをホストする各 BizTalk サーバーの Local computer\Other People ストア|  
|解読 (受信)|固有の秘密キー (.pfx)|各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダ パイプラインをホストする各 BizTalk サーバーの "現在のユーザー\個人用" ストア|  

## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、このトピックの手順を実行する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

### <a name="to-display-the-certificates-management-console"></a>証明書の管理コンソールを表示するには  

1.  をクリックして**開始**、 をクリックして**実行**、型**MMC**、 をクリック**OK**を開く、 **Microsoft 管理コンソール**.  

2.  をクリックして、**ファイル** メニューをクリック**スナップインの追加または削除**を表示する、**スナップインの追加または削除** ダイアログ ボックス。  

3.  をクリックして、**追加**を表示するボタン、**スタンドアロン スナップインの追加** ダイアログ ボックス。  

4.  選択**証明書**クリックして、スナップインの一覧から**追加**します。  

5.  選択**コンピューター アカウント**、 をクリックして**次**、順にクリックします**完了**。 これは追加、**証明書管理コンソール**のためのインターフェイス**ローカル コンピューター**します。  

6.  いることを確認**証明書**クリックして、スナップインの一覧が選択されている**追加**もう一度です。  

7.  選択 **[ユーザー アカウント**、] をクリックし、**完了**。 これは追加、**証明書管理コンソール**のためのインターフェイス**現在のユーザー**します。  

    > [!NOTE]  
    >  これが表示されます、**証明書管理コンソール**現在ログオンに使用しているアカウント。 サービス アカウントの個人証明書ストアに証明書をインポートする必要がある場合は、最初にサービス アカウントの資格情報を使用してログオンしてください。  

8.  をクリックして、**閉じる**のボタンでは、**スタンドアロン スナップイン** ダイアログ ボックス。  

9. をクリックして、 **OK**ボタンを**スナップインの追加または削除** ダイアログ ボックス。  

### <a name="to-install-a-certificate-for-receiving-encrypted-messages"></a>暗号化されたメッセージを受信するための証明書をインストールするには  

1. 証明機関 (CA) からのデジタル署名用の/秘密キー ペアを要求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用します。  

2. 公開キーの暗号化をパートナーに送信します。  

3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、パートナーからメッセージを受け取るハンドラーを実行するホスト インスタンスのサービス アカウントとしてログオンします。 サービス アカウントの個人用ストアに、メッセージを解読するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 秘密キー証明書をインストールします。  

   > [!NOTE]
   >  暗号化証明書をインストールするために使用する手順に関する詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)(<http://go.microsoft.com/fwlink/?LinkId=155156>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするために使用するツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155157>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

4. インストール パートナー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]適切なストアでメッセージを暗号化するための公開キー証明書。 パートナーは、Windows 2000 Server、Windows Server 2003、または Windows Server 2008 で使用されている場合、その他のユーザー ストアで公開キーをインストールします。  

### <a name="to-install-a-certificate-for-sending-encrypted-messages"></a>暗号化されたメッセージを送信するための証明書をインストールするには  

1. 証明機関 (CA) からの暗号化/秘密キー ペアを要求するパートナーがあります。  

2. パートナーに送信されるメッセージの暗号化用の公開キーを送信するパートナーがあります。  

3. 適切なストアでメッセージを解読するための秘密キー証明書をインストール パートナーがあります。 場合は、パートナーが Windows 2000 Server、Windows Server 2003、または Windows Server 2008 を使用して個人証明書ストアに秘密キーをインストールします。  

   > [!NOTE]
   >  暗号化証明書をインストールするために使用する手順に関する詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)(<http://go.microsoft.com/fwlink/?LinkId=155156>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするために使用するツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155157>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パートナーにメッセージを送信するハンドラーを実行しているホスト インスタンスがあるサーバーにログオンします。 その他のユーザー ストアにパートナーに送信されるメッセージを暗号化するため、パートナーの公開キー証明書をインストールします。  

### <a name="to-install-a-certificate-for-receiving-signed-messages"></a>署名付きメッセージを受信するための証明書をインストールするには  

1. 証明機関 (CA) からデジタル署名用の/秘密キー ペアを要求するパートナーがあります。  

2. デジタル署名用の公開キーを送信するパートナーがあります。  

3. その秘密適切なストアでメッセージの署名キー証明書をインストール パートナーがあります。 Windows 2000 Server、Windows Server 2003、または Windows Server 2008 を使用する場合に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストールしてある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

   > [!NOTE]
   >  暗号化証明書をインストールするために使用する手順に関する詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)([http://go.microsoft.com/fwlink/?LinkId=155156](http://go.microsoft.com/fwlink/?LinkId=155156)) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするために使用するツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155156>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、パートナーからメッセージを受信するハンドラーを実行しているホスト インスタンスがあるサーバーにログオンします。 その他のユーザー ストアに署名を検証するパートナーの公開キー証明書をインストールします。  

### <a name="to-install-a-certificate-for-sending-signed-messages"></a>署名付きメッセージを送信するための証明書をインストールするには  

1. 証明機関 (CA) からのデジタル署名用の/秘密キー ペアを要求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用します。  

2. デジタル署名の公開キーをパートナーに送信します。  

3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パートナーにメッセージを送信ハンドラーを実行するホスト インスタンスのサービス アカウントとしてログオンします。 インストール、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アカウントの個人用ストア内のメッセージに署名するための秘密キー証明書。  

   > [!NOTE]
   >  暗号化証明書をインストールするために使用する手順に関する詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)(<http://go.microsoft.com/fwlink/?LinkId=155156>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするために使用するツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155157>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

4. インストール パートナー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]適切なストアでデジタル署名を検証するための公開キー証明書。 パートナーは、Windows 2000 Server、Windows Server 2003、または Windows Server 2008 で使用されている場合、その他のユーザー ストアで公開キーをインストールします。
