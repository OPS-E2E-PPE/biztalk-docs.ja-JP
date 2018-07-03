---
title: EDI 処理におけるアグリーメントのロール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81b0449-6656-49f7-a781-5fd60031b3d5
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2125ca348cc8f333b1b223404371ae13b113fe1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980435"
---
# <a name="the-role-of-agreements-in-edi-processing"></a>EDI 処理におけるアグリーメントのロール
組織は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、1 つ以上の取引先との間で EDI メッセージを送受信します。 取引先は、組織内の Business Entities であるビジネス プロファイルを順番に定義します。 ビジネス プロファイルがメッセージを交換する方法は、2 つのビジネス プロファイル間の取引先アグリーメントとして定義されます。 詳細については、次を参照してください。 [、取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)します。  
  
 取引先アグリーメントは、取引先管理 (TPM) ユーザー インターフェイスで作成します。 TPM の画面はでは、**パーティ**のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="configuring-an-agreement-for-edi-processing"></a>EDI 処理のためのアグリーメントの構成  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して EDI メッセージを交換するすべての取引先は、通信パラメーターについて合意する必要があります。 その後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をホストする組織は TPM で取引先を作成し (自身の取引先を含む)、ビジネス プロファイルおよびビジネス プロファイル間の取引先アグリーメントを作成する必要があります。 取引先アグリーメントの一部として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が取引先のビジネス プロファイルと EDI メッセージを送受信する方法のプロパティを設定します。 その後、他の取引先でも同じことを行います。メッセージを交換するためには、構成が互換である必要があります。  
  
 EDI 通信用に以下のプロパティを定義する必要があります。  
  
- 名前、送信ポート、署名証明書など、取引先の全般的な性質を定義する取引先プロパティ。  
  
- ビジネス ID を定義する、ビジネス プロファイル プロパティ。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が取引先からの受信メッセージを処理する方法と、その取引先宛ての送信メッセージを生成する方法を定義する、取引先アグリーメントの一部としての EDI プロパティ。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での受信と送信の両方の AS2 通信の実行方法を定義する、取引先アグリーメントの一部としての AS2 プロパティ。 これらのプロパティは、EDI メッセージが AS2 上で通信されるときにのみ EDI 通信に影響を与えます。  
  
  > [!NOTE]
  >  同一のビジネス プロファイル間の AS2 アグリーメントおよび EDI メッセージング アグリーメントは、個別に指定されます。 この 2 つのアグリーメントが組み合わさり、パートナーシップを形成します。  
  
  取引先アグリーメントのプロパティは、以下の処理を決定します。  
  
- EDI エンベロープの処理と生成  
  
- 受信確認の処理と生成  
  
- 受信と送信の EDI メッセージの検証  
  
- バッチ作成  
  
- 状態レポート  
  
  ビジネス id に可能性があります、特定の値など**D-U-N-S (Dun & Bradstreet)** します。 固有の名前は、Duns に対して "01" というように、固有の修飾子を持ちます。 ビジネス ID 名が固有でない場合、X12 でエンコードされたメッセージでは "ZZ" を使用し、EDIFACT でエンコードされたメッセージでは "ZZZ" を使用します。これにより、互いに個別のエンティティによって定義されていることを示します。 この値と修飾子により、ビジネス プロファイルが識別されます。 ビジネス ID 名は情報提供のみを目的とし、BizTalk ランタイムでの処理に使用されることはありません。  
  
## <a name="determining-an-agreement-for-edi-processing"></a>EDI 処理のためのアグリーメントの決定  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDI メッセージを受信するたびに、メッセージの解決先となる取引先アグリーメントを特定しようと試みます。 アグリーメントの一部として定義されている送信者の修飾子、送信者の ID、受信者の修飾子、受信者の ID をメッセージと照合することで、取引先アグリーメントを解決しようとします。 このプロセスの詳細については、次を参照してください。[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信する EDI メッセージを生成するたびに、メッセージの送信先のビジネス プロファイルと関連付けられたアグリーメントを特定しようと試みます。 以下のいずれかを使用して、メッセージとアグリーメントを照合することで、アグリーメントを解決しようとします。  
  
- コンテキスト プロパティ AgreementPartIdForSend  
  
- コンテキスト プロパティ AgreementNameForSend、SenderPartyNameForSend、および ReceiverPartyNameForSend  
  
- 送信者の修飾子と ID、および受信者の修飾子と ID  
  
- 送信ポート名  
  
  このプロセスの詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。  
  
## <a name="using-edi-global-properties"></a>EDI グローバル プロパティの使用  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信メッセージまたは送信メッセージのアグリーメントを特定できない場合は、フォールバック アグリーメントを使用して、受信インターチェンジの処理や送信インターチェンジの生成を行います。 フォールバック アグリーメントの設定を右クリックして、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールとクリックして**X12 フォールバック設定**(X12 でエンコードされたメッセージ) 用または**EDIFACT フォールバックの設定**(EDIFACT でエンコードされたメッセージ)。 グローバル プロパティの詳細については、次を参照してください。[構成のグローバルまたはフォールバック アグリーメントのプロパティ](../core/configuring-global-or-fallback-agreement-properties.md)します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、インターチェンジのアグリーメントが特定できない場合のみ、フォールバック アグリーメントを使用します。 アグリーメントが特定された場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、2 つの取引先間のアグリーメントに定義されていないプロパティのフォールバック アグリーメントからのプロパティ値は使用しません。  
  
 フォールバック プロパティは、ポート設定で認証が必要な場合は使用されません。 受信ポートのポートの設定に認証が必要なかどうか (いずれか**認証が失敗した場合は、メッセージを削除**または**認証が失敗した場合は、メッセージを保持する**で選択した、**全般**のページ、**受信ポートのプロパティ** ダイアログ ボックス)、アグリーメントが、受信ポートで受信したインターチェンジ必要です。 この場合、フォールバック アグリーメントは使用されません。 インターチェンジのアグリーメントが特定できない場合、インターチェンジは認証が失敗したように扱われ、保留にされます。  
  
## <a name="see-also"></a>参照  
 [アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)   
 [アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)   
 [EDI のプロパティを構成します。](../core/configuring-edi-properties.md)   
 [グローバルまたはフォールバック アグリーメント プロパティの構成](../core/configuring-global-or-fallback-agreement-properties.md)   
 [EDI パーティに関する既知の問題](../core/known-issues-with-edi-parties.md)