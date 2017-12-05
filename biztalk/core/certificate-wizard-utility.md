---
title: "証明書ウィザード ユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b0341a11c45cd08f8476d48ea38cbf96bcc49c1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="certificate-wizard-utility"></a>証明書ウィザード ユーティリティ
.pfx ファイルまたは .cer ファイルの証明書をプライベート ストアまたはパブリック ストアにインポートして Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用できるようにするには、CertWizard ユーティリティを使用します。  
  
 証明書ウィザードのソース コードは含まれて、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダーです。 64 ビット オペレーティング システムとバージョンの BizTalk Server になります、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダーです。 Visual Studio を使用して構築するのに必要が最初に証明書ウィザードを使用します。  
  
 CertWizard は、.pfx ファイルの秘密キーを個人用ストアにインポートし、.cer ファイルの公開キーをパブリック ストアにインポートします。 秘密キーをインポートする場合は、着信メッセージの証明書に暗号化解除証明書を指定するか、送信メッセージの証明書に署名証明書を指定できます。  
  
 **構文の説明**  
  
 次の表に、CertWizard ユーティリティが使用する構文の各要素について説明します。  
  
|||  
|-|-|  
|構文|Description|  
|Privatekey|秘密キーをインポートするために使用します。|  
|Publickey|公開キーをインポートするために使用します。|  
|Rootkey|ルート キーを証明機関からインポートするために使用します。|  
|filename.pfx (または .cer)|.pfx (秘密キー) ファイルまたは .cer (公開キー) ファイルの完全なパス。|  
|Filepassword|.pfx ファイルのロックを解除するために必要なパスワード。|  
|Useridentity|1 つまたは複数の BizTalk ホストが使用するサービス ID。 ホストを指定せずに、ユーザー アカウントを使用して証明書をインポートするには、適切なユーザー アカウントを入力します。 **注:** Useridentity スイッチを追加しない場合、ユーティリティはインポートし、すべてのユーザーの証明書を設定します。 **注:** Useridentity スイッチを追加する値を入力しなかった場合は、WMI に自動的にユーザー id が生成されます。|  
|Password|サービス ID ユーザーのパスワード。|  
|Thumbprint|ファイルに複数の証明書が含まれている場合に使用する、特定の証明書の拇印。 **注:**公開証明書ファイルの場合、ファイルには複数の証明書が含まれていて、拇印を指定しないユーティリティ インポート ファイル内のすべての証明書。 プライベート証明書ファイルの場合は、インポートする証明書を選択するように求めるメッセージが表示されます。|  
|使用方法|インポートしたプライベート証明書の用途。 次のいずれかになります。<br /><br /> **サインオン**(の署名証明書の)<br /><br /> **復号化**(の暗号化解除証明書の)<br /><br /> **両方**(用の証明書を署名する証明書と暗号化解除証明書の両方)<br /><br /> **none** (用の証明書を署名する証明書と暗号化解除証明書の両方)。 **注:** /Usage スイッチを none に設定した場合、ウィザードが設定されていない証明書の拇印、BizTalk ホストと BizTalk グループにします。|  
|Exportable|指定できます**True**または**False**です。 場合**True**、秘密キーを再エクスポートできます。|  
  
 **秘密キーをインポートするための構文**  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 **公開キーをインポートするための構文**  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 **ルート キーをインポートするための構文**  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-run-the-certificate-wizard"></a>証明書ウィザードを実行するには  
  
1.  コマンド プロンプトを開きます。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities に移動します。  
  
3.  コマンド プロンプトで次のように入力します。 **CertWizard**、必須と適切なスイッチを入力して、キーを押します**Enter**です。  
  
    > [!NOTE]
    >  コマンド プロンプトで完全なコマンドを指定しないと、必須の値を指定するように求めるメッセージが表示されます。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)