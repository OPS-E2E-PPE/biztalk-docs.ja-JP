---
title: AS2 処理におけるアグリーメントのロール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6a6fe1-8fb4-4998-a1b4-aadad7e672c4
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6b5b93332f74743c4798f0ce821794d29e5262c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394051"
---
# <a name="the-role-of-agreements-in-as2-processing"></a>AS2 処理におけるアグリーメントのロール
組織は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、1 つ以上の取引先との間で AS2 メッセージを送受信します。 取引先は、組織内の Business Entities であるビジネス プロファイルを順番に定義します。 さまざまな取引先に属する 2 つのビジネス プロファイル間の双方向の取引先契約に AS2 プロパティを設定します。  
  
 取引先管理 (TPM) ユーザー インターフェイスでは、取引先契約を作成できます。 TPM の画面はでは、**パーティ**のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 ビジネス プロファイル、および、TPM ソリューションにまとめて契約同順位の取引方法の詳細についてを参照[、取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)します。  
  
## <a name="configuring-an-agreement-for-as2-processing"></a>AS2 処理のためのアグリーメントの構成  
 取引パートナーが別の取引パートナーから AS2 メッセージを受信するか、または別の取引パートナーに AS2 メッセージを送信すると、そのメッセージは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 受信パイプラインまたは AS2 送信パイプラインによって 2 つの取引パートナー間の AS2 アグリーメントのプロパティに基づいて処理されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信と送信の両方の AS2 通信を行う方法を定義する AS2 プロパティを構成できます。  
  
> [!NOTE]
>  EDI 処理とは異なり、アグリーメントを特定できない場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用できるフォールバック AS2 アグリーメントはありません。 AS2 受信または送信パイプラインは、アグリーメントが特定された場合にのみメッセージを処理します。  
> 
> [!NOTE]
>  AS2 アグリーメントは、EDI アグリーメントとは別に構成されます。 ドキュメントを受信すると、AS2 アグリーメントは AS2 処理時に解決され、それとは別に EDI アグリーメントが EDI 処理時に解決されます。 両方のアグリーメントにより、パートナーシップが形成されます。 詳細については、次を参照してください。[取引先アグリーメント](../core/trading-partner-agreement.md)します。  
> 
> [!NOTE]
>  名前やエイリアス、送信ポート、署名証明書など、パーティの全般的な側面を定義するプロパティは、取引先プロパティの一部に指定されます。  
  
 HTTP/HTTPS トランスポートは、EDIINT/AS2 でエンコードされたメッセージにも AS2 を経由して非 EDI でエンコードされたメッセージにも使用できます。 EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS トランスポート経由で送信すると、アグリーメントの EDI プロパティが適用されます。  
  
 ホーム組織の署名証明書がで定義されている、**証明書**のページ、 **BizTalk グループ - グループのプロパティ** ダイアログ ボックス。 さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定のアグリーメントのプロパティの一部として、証明書を定義することで AS2 メッセージ用の証明書の署名をオーバーライドすることができます。  特定のアグリーメントを別の証明書を定義するには、使用、**署名証明書**一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 別の証明書を指定する方法については、次を参照してください。[署名証明書を構成 (AS2)](../core/configuring-signature-certificates-as2.md)します。  
  
## <a name="determining-an-agreement-for-as2-processing"></a>AS2 処理のためのアグリーメントの決定  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、AS2 でエンコードされたメッセージを受信すると、AS2-From ヘッダーをパーティの一方向アグリーメントの AS2-From アグリーメント設定と照合することにより、メッセージを送信したパーティの決定を試みます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、AS2 でエンコードされたメッセージを送信すると、AS2-To ヘッダーをパーティの一方向アグリーメントの AS2-To アグリーメントのプロパティと照合することにより、メッセージを受信するパーティの決定を試みます。 詳細については、次を参照してください。[受信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-incoming-as2-messages.md)または[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)します。  
  
## <a name="see-also"></a>参照  
 [受信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-incoming-as2-messages.md)   
 [送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)   
 [AS2 プロパティの構成](../core/configuring-as2-properties.md)