---
title: アグリーメントの解決と送信 EDI メッセージ スキーマの決定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37aeb9d-1e95-464d-bb71-73653c1d4674
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e9d652e352fb7bc3d18ae83f04784d8e112b2ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359994"
---
# <a name="agreement-resolution-and-schema-determination-for-outgoing-edi-messages"></a>送信 EDI メッセージのアグリーメントの解決とスキーマの決定
取引先に EDI メッセージを生成するには、EDI 送信パイプラインは、次の操作を行う必要があります。  
  
-   メッセージが解決されるアグリーメントを特定します。  
  
-   メッセージの検証に使用するスキーマを決定します。  
  
## <a name="agreement-resolution"></a>アグリーメントの解決  
 EDI 送信パイプラインは、一連の送信インターチェンジとアグリーメントのプロパティ間の一致があるかどうかを判断する手順を実行することで、アグリーメント参照を実行します。 1 回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントが決定されます (下記参照) のインターチェンジに適用されるドキュメント スキーマを決定します。 生成および送信メッセージを検証する、一致するアグリーメントと関連するスキーマに関連付けられたプロパティを使用します。  
  
 アグリーメントの解決を実行する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のように進みます。  
  
1. AgreementPartIDForSend コンテキスト プロパティは、一方向のアグリーメントの ID と照合してアグリーメントを解決します。 このプロパティは、整数型、カスタム コンポーネントで設定できます。設定されていない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
2. 手順 1. が成功しなかった場合は、すべて以下 3 つのコンテキスト プロパティでアグリーメントのプロパティを照合してアグリーメントを解決します。AgreementNameForSend、SenderPartyNameForSend、ReceiverPartyNameForSend します。 アグリーメントを正常に解決するには 3 つすべてのプロパティを設定する必要がありますに注意してください。 カスタム コンポーネントでこれらのプロパティを設定できます。設定されていない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
3. 手順 2. が成功しなかった場合は、メッセージ コンテキスト プロパティで、その他のアグリーメント リゾルバーとして設定された DestinationPartyName プロパティのパーティ名を照合してアグリーメントを解決、**識別子**のタブアグリーメントのプロパティ。  
  
4. 手順 3 が成功しなかった場合は、アグリーメントのプロパティと、メッセージのコンテキストでは、次のプロパティを照合することで、アグリーメントを解決します。DestinationPartySenderIdentifier、DestinationPartySenderQualifier、DestinationPartyReceiverIdentifier、および DestinationPartyReceiverQualifier します。 アグリーメントを正常に解決するには 4 つすべてのプロパティを設定する必要がありますに注意してください。 カスタム コンポーネントでこれらのプロパティを設定できます。設定されていない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、以下を参照してください。  
  
   > [!NOTE]
   >  上記のセットのコンテキスト プロパティのいずれかが昇格される場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、これらのコンテキスト プロパティに関連するアグリーメントを検索するようになって[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを中断します。  
   > 
   >  ユーザーが意図的にアグリーメントの解決のコンテキスト プロパティのセットを作成し、リゾルバーが OnewayAgreement を識別するために失敗した場合は、メッセージは中断されます。 コンテキスト プロパティのセットに基づいてアグリーメントを解決するのには失敗した場合、対応する警告メッセージがイベント ログでスローされます。  
  
5. 手順 4. が成功せず、または昇格上記のコンテキスト プロパティのいずれも、EDI メッセージがアグリーメントに解決アグリーメントに関連付けられている送信ポートとメッセージをサブスクライブした送信ポートを照合することによりします。  
  
   > [!NOTE]
   >  1 つの送信ポートは複数のアグリーメントに関連付けられている場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エラーが生成されます。  
  
6. 1、2、3、または 4 の手順でアグリーメントが見つからない場合、送信パイプラインはフォールバック アグリーメント設定を使用して、送信メッセージの生成します。  
  
   **送信者と受信者のコンテキスト プロパティ照合によるアグリーメントの解決**  
  
   2 番目の手順では、一致に使用される 4 つのコンテキスト プロパティは、EDI が。DestinationPartySenderIdentifier、EDI を使用します。DestinationPartySenderQualifier、EDI を使用します。DestinationPartyReceiverIdentifier、および EDI です。DestinationPartyReceiverQualifier します。 これらのコンテキスト プロパティの名前空間は`http://schemas.microsoft.com/Edi/PropertySchema`します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] これらの値を関連する送信者と受信者の識別子と一方向アグリーメント プロパティの修飾子と一致を試みます。 これらのフィールドは isa05、isa06、isa07、および ISA08 x12 の場合、**識別子**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ**; ダイアログ ボックス、UNB2.1、UNB2.2、EDIFACT の場合、これらのフィールドUnb3.1、および unb3.2 で、**識別子**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
   すべてを使用して送信側アグリーメントの解決を有効にするすべての 4 つのコンテキスト プロパティを設定する必要があります 4 つの送信者と受信者の識別子と修飾子、します。 一意に行うには、アグリーメントが識別されます。 アグリーメント参照には、このメソッドを使用してより柔軟で送信側の処理。 などをこのメソッドでは、状況によっては、複数の送信ポートを作成しないようにしたり、複雑な送信ポート フィルターを回避するために、有効可能性があります。 これは、こともできます、OneWayAgreementId プロパティの設定を回避するために必要な場合。  
  
   メッセージは、すべての 4 つのコンテキスト プロパティが設定されているこれらのコンテキスト プロパティと property プロパティの間で一致が見つからない場合は、メッセージは中断されます。 すべての 4 つのコンテキスト プロパティが設定されていない場合にのみ、アグリーメントに関連付けられている送信ポートを使用して、アグリーメントが解決されます。  
  
> [!NOTE]
>  EDI パイプライン内のメッセージは次の手順にアグリーメントで解決、メッセージがアグリーメントを持つ有効な状態の手順に解決されるまでします。 たとえば場合は、メッセージがアグリーメントの解決の最初の手順で解決を取得しますが、アグリーメントが無効の状態が次の解決手順をメッセージが通過します。  
  
## <a name="schema-determination"></a>スキーマの決定  
 EDI 送信パイプラインは、各トランザクション セット (ドキュメントの種類情報またはルート ノード内) の中間 XML ファイルに含まれているスキーマの名前空間とスキーマの名前から、メッセージに該当するスキーマを決定します。  
  
 インターチェンジを保存されている個々 のトランザクションでドキュメントの種類の情報が中間 XML ファイルの完全なインターチェンジの設定、送信パイプラインは使用できます。 エンベロープ セグメントを処理するための制御セグメントのスキーマを使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)