---
title: HTTP アダプタのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, HTTP adapters
- configuring [HTTP adapters], security
- HTTP adapters, security
ms.assetid: ef6043c2-c62a-40e5-b2e1-53e60f87a761
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb4ad155eed3788a76bdf8cdd342750f45dfe72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992748"
---
# <a name="http-adapter-security-recommendations"></a>HTTP アダプタのセキュリティに関する推奨事項
HTTP アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] とアプリケーション間で HTTP (Hypertext Transfer Protocol) を介して情報を交換するために使用します。 アプリケーションは、指定された HTTP URL に HTTP POST 要求または HTTP GET 要求を送信することで、サーバーにメッセージを送信できます。 HTTP アダプターの詳細については、次を参照してください。 [HTTP アダプター](../core/http-adapter.md)します。 HTTP アダプターをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
- HTTP アダプター用にインターネット インフォメーション サービス (IIS) の設定を構成するようにします。 詳細については、次を参照してください。 [IIS の HTTP 受信場所を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)します。  
  
- 7.0 を使用する場合は、アプリケーションの分離を構成するための IIS 7.0 の推奨事項に従うことを確認します。  
  
- 基本認証を使用する場合、またはメッセージ レベルでの暗号化を使用しない場合、メッセージの送受信両方に Secure Sockets Layer (SSL) を使用して、未認証のユーザーがユーザーの資格情報をスニッフィングできないようにすることをお勧めします。  
  
- メッセージの送受信に Windows 統合認証を使用することをお勧めします。  
  
- ISAPI 拡張ファイルの名前変更、コピー、または移動を実行しないことをお勧めします。 これにより、セキュリティ更新プログラムのインストーラーが、このファイルに関連する可能性のあるセキュリティ更新プログラムを正しく適用できます。  
  
- 強力な随意アクセス制御リスト (DACL) を、ISAPI 拡張ファイルを含むディレクトリおよびメッセージの受信用に作成する仮想ディレクトリに使用する必要があります。 HTTP アダプターを実行しているホストの BizTalk 分離ホスト グループのメンバーには、読み取りと実行のアクセス許可が必要です。また、HTTP アダプターが認証するユーザーには、これらのディレクトリに対する読み取りアクセス許可が必要です。  
  
- HTTP 送信アダプターで SSL クライアント証明書を使用する場合は、これらの証明書を手動で構成する必要があります。  
  
- 他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントと同様に、HTTP アダプターは、境界ネットワークに配置しないことをお勧めします。 境界ネットワークに配置する場合、境界ネットワークのポートを、メッセージ ボックス データベースへの SQL Server トラフィック用のデータ ドメインに開く必要がありますが、これにはリスクが伴います。 HTTP アダプターは、処理ドメイン (つまり、境界ネットワーク以外) で構成することをお勧めします。 処理ドメインで構成したら、最も外側のファイアウォール (FW4) を、処理ドメイン内のファイアウォール (FW3) 経由で HTTP 要求を転送するように構成できます。 この場合、境界ネットワーク内に IIS は必要ありません。 このメカニズムはリバース プロキシと呼ばれます (Forefront Threat Management Gateway (TMG) 2010 サーバー実装では「Web 公開」と呼ばれます)。  
  
- HTTP 受信場所にアプリケーション プールを作成する場合、HTTP 受信アダプターを実行している分離ホストの Windows グループおよびインターネット インフォメーション サービスのワーカー プロセス グループ (IIS_WPG group) のメンバーであるアカウントで実行するように構成する必要があります。 その後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、HTTP 受信アダプターのホスト インスタンスでこのアカウントを使用するように構成する必要があります。 IIS_WPG グループのアカウントを変更する場合は、新しいアカウントで実行されるようにホスト インスタンスを更新する必要もあります。 詳細については、次を参照してください。 [IIS の HTTP 受信場所を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)します。  
  
## <a name="see-also"></a>参照  
 [受信と送信サーバーのポート](../core/ports-for-the-receive-and-send-servers.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)