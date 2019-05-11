---
title: CertWizard |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b028deda4ef180a4983e1c58fa7a9487804a0232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284779"
---
# <a name="certwizard"></a>CertWizard
CertWizard ユーティリティを使用して Microsoft® で使用するためのプライベートまたはパブリック ストアに .pfx または .cer ファイルから証明書をインポートする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\  
  
## <a name="running-certwizard"></a>CertWizard の実行  
  
#### <a name="to-run-certwizard"></a>CertWizard を実行するには  
  
1. コマンド プロンプトを開きます。  
  
2. 移動\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  
  
3. コマンド プロンプトで「 **CertWizard**と、必須および適切なスイッチを入力し、ENTER キーを押します。  
  
## <a name="syntax-for-certwizard"></a>CertWizard の構文  
 次に、このコマンドライン ユーティリティを起動するために使用する構文を示します。  
  
### <a name="syntax-for-importing-a-private-key"></a>秘密キーをインポートするための構文  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a>公開キーをインポートするための構文  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a>ルート キーをインポートするための構文  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a>構文の説明  
 次の表では、CertWizard ユーティリティを使用する構文の各部について説明します。  
  
|**構文**|**[説明]**|  
|----------------|---------------------|  
|**プライベート キー**|秘密キーをインポートするために使用します。|  
|**公開鍵**|公開キーをインポートするために使用します。|  
|**Rootkey**|ルート キーのインポートに使用される、証明機関から。|  
|**filename.pfx (または .cer)**|.Pfx (秘密キー) または .cer (公開キー) ファイルの完全パス。|  
|**Filepassword**|.Pfx ファイルのロック解除に必要なパスワード。|  
|**割り当てられていません**|1 つまたは複数の BizTalk ホストを使用するサービス id を指定します。 ホストを指定したくないが、ユーザー アカウントで証明書をインポートする場合は、ユーザー アカウントを入力します。 **注:** 追加しない場合、 **Useridentity**切り替えるには、このユーティリティをインポートし、すべてのユーザーの証明書を設定します。 **注:** 追加する場合、 **Useridentity**切り替えるが、値を入力しない WMI は、ユーザー id を自動的に生成されます。|  
|**Password**|サービス id ユーザーのパスワード。|  
|**拇印**|ファイルの場合も、特定の証明書の拇印には、1 つ以上の証明書が含まれています。 **注:** 公開証明書ファイルの場合、ファイルには、1 つ以上の証明書が含まれていて、拇印を指定しない場合、ユーティリティは、ファイル内のすべての証明書をインポートします。 プライベート証明書ファイルの場合、ユーティリティにインポートする証明書を選択するように求められます。|  
|**使用方法**|インポートしたプライベート証明書の用途。 Sign (署名証明書の場合)、decrypt (暗号化解除証明書)、両方 (証明書の署名証明書と暗号化解除証明書の両方である)、または none (も証明書は署名証明書と暗号化解除証明書の両方を指定できます。). **注:** 設定した場合、 **/Usage**スイッチを none に、ウィザードでは、BizTalk ホストと BizTalk グループに証明書の拇印は設定しません。|  
|**エクスポート可能**|`True`または`False`します。 場合`True`、秘密キーを再エクスポートできます。|  
  
## <a name="remarks"></a>コメント  
 CertWizard は、個人用ストアに秘密キーを .pfx ファイルからインポートし、.cer ファイルから公開キーをパブリック ストアにインポートします。 秘密キーをインポートするときに、証明書は受信メッセージの復号化証明書または送信メッセージの署名証明書を指定できます。  
  
 CertWizard は、コマンド プロンプトで完全なコマンドを指定しないと、必要な値を指定することが求められます。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [CertWizard ユーティリティを使用した証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)
