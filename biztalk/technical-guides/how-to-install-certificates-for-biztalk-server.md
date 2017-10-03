---
title: "BizTalk Server の証明書をインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70a89595-8828-4872-b78b-77e9b0b048b8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d799956d25bfe8e494fcbc2fbc6cbea770a92fdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-certificates-for-biztalk-server"></a>BizTalk Server の証明書をインストールする方法
セキュリティで保護するデータの転送で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、適切な証明書ストアに適切な証明書を追加して、証明書を適切な BizTalk アイテムに関連付ける必要があります。 このトピックでは、ローカル コンピューターと現在のユーザーの証明書ストアの証明書 管理コンソール インターフェイスを表示する方法と、適切なストアで適切な証明書をインストールする方法について説明します。  
  
 次の表に示すように証明書は、サインインのヘルプの署名を確認、暗号化、およびメッセージの解読に使用されます。  
  
|証明書の使用|証明書の種類|証明書ストア|  
|-----------------------|----------------------|-----------------------|  
|署名 (送信)|固有の秘密キー (.pfx)|現在のユーザー\\<br />各ホスト インスタンス サービス アカウントとして MIME/SMIME エンコーダー パイプラインをホストする各 BizTalk サーバーの個人用ストア|  
|署名の検証 (受信)|取引先の公開キー (.cer)|各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダ パイプラインをホストする各 BizTalk サーバーの Local computer\Other People ストア|  
|暗号化 (送信)|取引先の公開キー (.cer)|MIME/SMIME エンコーダ パイプラインをホストする各 BizTalk サーバーの Local computer\Other People ストア|  
|解読 (受信)|固有の秘密キー (.pfx)|各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダ パイプラインをホストする各 BizTalk サーバーの "現在のユーザー\個人用" ストア|  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、このトピックの手順を実行する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-display-the-certificates-management-console"></a>証明書管理コンソールを表示するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**MMC**、 をクリック**OK**を開くには、 **Microsoft 管理コンソール**.  
  
2.  クリックして、**ファイル** メニューをクリックして**スナップインの追加または削除**を表示する、**スナップインの追加または削除** ダイアログ ボックス。  
  
3.  クリックして、**追加**を表示するボタン、**スタンドアロン スナップインの追加** ダイアログ ボックス。  
  
4.  選択**証明書**クリックして、スナップインの一覧から**追加**です。  
  
5.  選択**コンピューター アカウント**、 をクリックして**次へ**をクリックし、**完了**です。 これは追加、**証明書管理コンソール**のためのインターフェイス**ローカル コンピューター**です。  
  
6.  いることを確認**証明書**クリックして、スナップインの一覧から選択されている**追加**もう一度です。  
  
7.  選択**ユーザー アカウント**、クリックして**完了**です。 これは追加、**証明書管理コンソール**のためのインターフェイス**現在のユーザー**です。  
  
    > [!NOTE]  
    >  これが表示されます、**証明書管理コンソール**現在ログオンに使用しているアカウントにします。 サービス アカウントの個人証明書ストアに証明書をインポートする必要がある場合は、最初にサービス アカウントの資格情報を使用してログオンしてください。  
  
8.  クリックして、**閉じる**のボタンでは、**スタンドアロン スナップイン** ダイアログ ボックス。  
  
9. をクリックして、 **OK**ボタンをクリックして、**スナップインの追加または削除** ダイアログ ボックス。  
  
### <a name="to-install-a-certificate-for-receiving-encrypted-messages"></a>暗号化されたメッセージを受信するための証明書をインストールするには  
  
1.  証明機関 (CA) からのデジタル署名用と非公開のキー ペアを要求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用します。  
  
2.  公開キー暗号化のパートナーに送信します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、パートナーからメッセージを受信するハンドラーを実行しているホスト インスタンスのサービス アカウントとしてログオンします。 サービス アカウントの個人用ストアに、メッセージを解読するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 秘密キー証明書をインストールします。  
  
    > [!NOTE]  
    >  暗号化の証明書をインストールする手順の詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)(http://go.microsoft.com/fwlink/?LinkId=155156) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするためのツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155157) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
4.  インストール パートナー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]適切なストア内のメッセージを暗号化するための公開キー証明書。 パートナーは、Windows 2000 Server、Windows Server 2003 または Windows Server 2008 で使用されている場合、その他のユーザーのストアで公開キーをインストールします。  
  
### <a name="to-install-a-certificate-for-sending-encrypted-messages"></a>暗号化されたメッセージを送信するための証明書をインストールするには  
  
1.  証明機関 (CA) からの暗号化プライベートの公開キーのペアを要求、パートナーがあります。  
  
2.  パートナーに送信するメッセージを暗号化するための公開キーを送信するパートナーがあります。  
  
3.  適切なストア内のメッセージを解読するための秘密キー証明書をインストール パートナーがあります。 パートナーは、Windows 2000 Server、Windows Server 2003 または Windows Server 2008 で使用されている場合、個人証明書ストアに秘密キーをインストールします。  
  
    > [!NOTE]  
    >  暗号化の証明書をインストールする手順の詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)(http://go.microsoft.com/fwlink/?LinkId=155156) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするためのツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155157) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パートナーにメッセージを送信するハンドラーを実行しているホスト インスタンスがあるサーバーにログオンします。 その他のユーザーのストアにパートナーに送信されたメッセージを暗号化するため、パートナーの公開キー証明書をインストールします。  
  
### <a name="to-install-a-certificate-for-receiving-signed-messages"></a>署名付きメッセージを受信するための証明書をインストールするには  
  
1.  証明機関 (CA) からのデジタル署名用と非公開のキー ペアを要求、パートナーがあります。  
  
2.  デジタル署名用の公開キーを送信するパートナーがあります。  
  
3.  適切なストアでメッセージの署名に秘密キー証明書をインストール パートナーがあります。 Windows 2000 Server、Windows Server 2003 または Windows Server 2008 を使用する場合に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストールしてある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
    > [!NOTE]  
    >  暗号化の証明書をインストールする手順の詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)([http://go.microsoft.com/fwlink/?LinkId=155156](http://go.microsoft.com/fwlink/?LinkId=155156)) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするためのツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155156) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、パートナーからメッセージを受信するハンドラーを実行しているホスト インスタンスがあるサーバーにログオンします。 その他のユーザー ストアに署名を検証する、パートナーの公開キー証明書をインストールします。  
  
### <a name="to-install-a-certificate-for-sending-signed-messages"></a>署名付きメッセージを送信するための証明書をインストールするには  
  
1.  証明機関 (CA) からのデジタル署名用と非公開のキー ペアを要求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用します。  
  
2.  デジタル署名の公開キーをパートナーに送信します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パートナーにメッセージを送信するハンドラーを実行しているホスト インスタンスのサービス アカウントとしてログオンします。 インストール、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アカウントの個人用ストアでメッセージの署名に秘密キー証明書。  
  
    > [!NOTE]  
    >  暗号化の証明書をインストールする手順の詳細については、次を参照してください。[メッセージの暗号化の証明書をインストールする方法](http://go.microsoft.com/fwlink/?LinkId=155156)(http://go.microsoft.com/fwlink/?LinkId=155156) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。 証明書ストアに証明書をインポートするためのツールの詳細については、次を参照してください。[証明書ウィザード ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155157) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
4.  インストール パートナー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]適切なストアでデジタル署名を検証するための公開キー証明書。 パートナーは、Windows 2000 Server、Windows Server 2003 または Windows Server 2008 で使用されている場合、その他のユーザーのストアで公開キーをインストールします。