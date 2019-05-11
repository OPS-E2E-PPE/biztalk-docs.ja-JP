---
title: 証明書のウィザード ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff147004773bfb620898f5e381fd242a6416f158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357559"
---
# <a name="certificate-wizard-utility"></a>証明書ウィザード ユーティリティ
CertWizard ユーティリティを使用して Microsoft で使用するためのプライベートまたはパブリック ストアに .pfx または .cer ファイルから証明書をインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 証明書ウィザードのソース コードが記載されて、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダー。 64 ビット オペレーティング システムとバージョンの BizTalk Server を使用するが、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダー。 Visual Studio を使用してビルドするのに必要がありますまず証明書ウィザードを使用します。  
  
 CertWizard は、個人用ストアに秘密キーを .pfx ファイルからインポートし、.cer ファイルから公開キーをパブリック ストアにインポートします。 秘密キーをインポートするときに、証明書は受信メッセージの復号化証明書または送信メッセージの署名証明書を指定できます。  
  
 **構文の説明**  
  
 次の表では、CertWizard ユーティリティを使用する構文の各部について説明します。  
  
|||  
|-|-|  
|構文|説明|  
|プライベート キー|秘密キーをインポートするために使用します。|  
|公開鍵|公開キーをインポートするために使用します。|  
|Rootkey|ルート キーのインポートに使用される、証明機関から。|  
|filename.pfx (または .cer)|.Pfx (秘密キー) または .cer (公開キー) ファイルの完全パス。|  
|Filepassword|.Pfx ファイルのロック解除に必要なパスワード。|  
|割り当てられていません|1 つまたは複数の BizTalk ホストを使用するサービス id を指定します。 ホストを指定したくないが、ユーザー アカウントで証明書をインポートする場合は、ユーザー アカウントを入力します。 **注:** Useridentity スイッチを追加しないと、ユーティリティはインポートし、すべてのユーザーの証明書を設定します。 **注:** Useridentity スイッチを追加する値を入力しない場合は、WMI では、ユーザー id が自動的に生成します。|  
|パスワード|サービス id ユーザーのパスワード。|  
|Thumbprint|ファイルの場合も、特定の証明書の拇印には、1 つ以上の証明書が含まれています。 **注:** 公開証明書ファイルの場合、ファイルには、1 つ以上の証明書が含まれていて、拇印を指定しない場合、ユーティリティは、ファイル内のすべての証明書をインポートします。 プライベート証明書ファイルの場合、ユーティリティにインポートする証明書を選択するように求められます。|  
|使用方法|インポートしたプライベート証明書の用途。 次のいずれかになります。<br /><br /> **サインオン**(の署名証明書)<br /><br /> **復号化**(の復号化証明書)<br /><br /> **どちらも**(の署名証明書と暗号化解除証明書の両方である証明書)<br /><br /> **none** (用証明書を署名証明書と暗号化解除証明書の両方)。 **注:**/Usage スイッチを none に設定した場合、ウィザードでは、BizTalk ホストと BizTalk グループでの証明書の拇印は設定しません。|  
|エクスポート可能|**True**または**False**します。 場合**True**、秘密キーを再エクスポートできます。|  
  
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
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-run-the-certificate-wizard"></a>証明書ウィザードを実行するには  
  
1. コマンド プロンプトを開きます。  
  
2. 移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \utilities します。  
  
3. コマンド プロンプトで「 **CertWizard**、入力必須および適切なスイッチ、およびキーを押します**Enter**します。  
  
   > [!NOTE]
   >  CertWizard は、コマンド プロンプトで完全なコマンドを指定しないと、必要な値を指定することが求められます。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)