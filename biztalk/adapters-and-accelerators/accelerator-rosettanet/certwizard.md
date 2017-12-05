---
title: "CertWizard |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea106299a734f79506823ca4a6951a3dad367553
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="certwizard"></a>CertWizard
.pfx ファイルまたは .cer ファイルの証明書をプライベート ストアまたはパブリック ストアにインポートして [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] で使用できるようにするには、CertWizard ユーティリティを使用します。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\  
  
## <a name="running-certwizard"></a>CertWizard の実行  
  
#### <a name="to-run-certwizard"></a>CertWizard を実行するには  
  
1.  コマンド プロンプトを開きます。  
  
2.  移動\<*ドライブ*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\です。  
  
3.  コマンド プロンプトで次のように入力します。 **CertWizard**、必須と適切なスイッチを入力して、ENTER キーを押します。  
  
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
 次の表に、CertWizard ユーティリティが使用する構文の各要素について説明します。  
  
|**構文**|**Description**|  
|----------------|---------------------|  
|**プライベート キー**|秘密キーをインポートするために使用します。|  
|**公開キー**|公開キーをインポートするために使用します。|  
|**ルートキー**|ルート キーを証明機関からインポートするために使用します。|  
|**filename.pfx (または .cer)**|.pfx (秘密キー) ファイルまたは .cer (公開キー) ファイルの完全なパス。|  
|**Filepassword**|.pfx ファイルのロックを解除するために必要なパスワード。|  
|**割り当てられていません**|1 つまたは複数の BizTalk ホストが使用するサービス ID。 ホストを指定せずに、ユーザー アカウントを使用して証明書をインポートするには、適切なユーザー アカウントを入力します。 **注:**を追加しない場合、 **Useridentity**切り替えるには、ユーティリティによってインポートし、すべてのユーザーの証明書を設定します。 **注:**を追加する場合、 **Useridentity**切り替えるには、ですが、値を入力しない WMI は、ユーザー id を自動的に生成されます。|  
|**Password**|サービス ID ユーザーのパスワード。|  
|**拇印**|ファイルに複数の証明書が含まれている場合に使用する、特定の証明書の拇印。 **注:**公開証明書ファイルの場合、ファイルには複数の証明書が含まれていて、拇印を指定しないユーティリティ インポート ファイル内のすべての証明書。 プライベート証明書ファイルの場合は、インポートする証明書を選択するように求めるメッセージが表示されます。|  
|**使用方法**|インポートしたプライベート証明書の用途。 sign (署名証明書に使用可能)、decrypt (暗号化解除証明書に使用可能)、both (署名証明書と暗号化解除証明書のいずれでもある証明書に使用可能)、または none (署名証明書と暗号化解除証明書のいずれでもある証明書に使用可能) を指定できます。 **注:**設定した場合、 **/Usage**スイッチを none に、ウィザードでは、BizTalk ホストと BizTalk グループに証明書の拇印は設定しません。|  
|**エクスポート可能**|Can be `True` or `False`. `True` に指定すると、秘密キーを再エクスポートできます。|  
  
## <a name="remarks"></a>解説  
 CertWizard は、.pfx ファイルの秘密キーを個人用ストアにインポートし、.cer ファイルの公開キーをパブリック ストアにインポートします。 秘密キーをインポートする場合は、着信メッセージの証明書に暗号化解除証明書を指定するか、送信メッセージの証明書に署名証明書を指定できます。  
  
 コマンド プロンプトで完全なコマンドを指定しないと、必須の値を指定するように求めるメッセージが表示されます。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [CertWizard ユーティリティを使用した証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)