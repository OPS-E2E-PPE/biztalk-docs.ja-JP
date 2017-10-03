---
title: "AS2 アグリーメント プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.as2agreement.properties
ms.assetid: a62d8d2a-0b8d-4179-a48f-92f135b5787d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6f09f85b726869e98712abf354ad3943ce97a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-as2-agreement-properties"></a>AS2 アグリーメントのプロパティの構成
このセクションでは、AS2 トランスポート アグリーメントのプロパティについて説明します。 トランスポート プロトコルの設定の一部として、メッセージに署名する必要があるかどうか、メッセージを暗号化する必要があるかどうか、なども定義できます。  
  
> [!NOTE]
>  AS2 アグリーメントの構成は省略可能です。 AS2 アグリーメントにより、AS2 プロトコルによるメッセージの転送方法が定義されます。 取引先の判断により他のプロトコルを使用してメッセージを転送する場合は、AS2 アグリーメントを定義しないことを選択できます。 ただし、その場合の取引先は、メッセージの形式とエンコード方法を制御するエンコード アグリーメントを定義する必要があります。 エンコード アグリーメントの詳細については、次を参照してください。[エンコード アグリーメントのプロパティを構成する](../core/configuring-encoding-agreement-properties.md)です。  
  
> [!IMPORTANT]
>  アグリーメントの AS2 設定を変更するたびに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト インスタンスを再起動して変更を有効にする必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)  
  
-   [識別子 (AS2) の構成](../core/configuring-identifiers-as2.md)  
  
-   [検証の構成 (AS2)](../core/configuring-validation-as2.md)  
  
-   [受信確認 (MDN) の構成 (AS2)](../core/configuring-acknowledgements-mdns-as2.md)  
  
-   [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)  
  
-   [(AS2) の署名証明書を構成します。](../core/configuring-signature-certificates-as2.md)  
  
-   [送信ポートの関連付け (AS2) を構成します。](../core/configuring-send-port-association-as2.md)  
  
## <a name="see-also"></a>参照  
 [AS2 のプロパティを構成します。](../core/configuring-as2-properties.md)