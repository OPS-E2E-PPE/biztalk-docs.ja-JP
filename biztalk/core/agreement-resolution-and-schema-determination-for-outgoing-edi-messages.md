---
title: "アグリーメントの解決と送信 EDI メッセージのスキーマの決定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e37aeb9d-1e95-464d-bb71-73653c1d4674
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d33715d4f1683910269adf7b49965e31bce4840
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-resolution-and-schema-determination-for-outgoing-edi-messages"></a>送信 EDI メッセージのアグリーメントの解決とスキーマの決定
取引先への EDI メッセージを生成するには、EDI 送信パイプラインは次の作業を行う必要があります。  
  
-   メッセージの解決先となるアグリーメントを指定する。  
  
-   メッセージの検証に使用するスキーマを指定する。  
  
## <a name="agreement-resolution"></a>アグリーメント解決  
 EDI 送信パイプラインは、送信インターチェンジとアグリーメントのプロパティとの間に一致があるかどうかを判断する一連の手順を実行することで、アグリーメントの参照を実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってアグリーメントが特定されると、次に、そのインターチェンジに適用されるドキュメント スキーマが特定されます (後述)。 一致するアグリーメントに関連付けられたプロパティと関連するスキーマを使用して、送信メッセージの生成と検証が行われます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がアグリーメント解決を実行する手順は、次のとおりです。  
  
1.  AgreementPartIDForSend コンテキスト プロパティを一方向アグリーメントの ID と照合してアグリーメントを解決します。 このプロパティには整数型を指定する必要があり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではなくカスタム コンポーネントで設定できます。  
  
2.  手順 1. で一致するものが見つからない場合は、3 つのコンテキスト プロパティ (AgreementNameForSend、SenderPartyNameForSend、および ReceiverPartyNameForSend) すべてをアグリーメントのプロパティと照合して、アグリーメントを解決します。 アグリーメントを正しく解決するには、3 つのプロパティがすべて設定されている必要があります。 これらのプロパティは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではなくカスタム コンポーネントで設定できます。  
  
3.  手順 2. が成功しなかった場合での他のアグリーメント リゾルバーとして設定されている DestinationPartyName プロパティを使用して、メッセージ コンテキスト プロパティのパーティ名を照合することで、アグリーメントを解決、**識別子**のタブアグリーメントのプロパティです。  
  
4.  手順 3. で一致するものが見つからない場合は、メッセージのコンテキスト内の DestinationPartySenderIdentifier、DestinationPartySenderQualifier、DestinationPartyReceiverIdentifier、および DestinationPartyReceiverQualifier プロパティを、アグリーメントのプロパティと照合して、アグリーメントを解決します。 アグリーメントを正しく解決するには、4 つのプロパティがすべて設定されている必要があります。 カスタム コンポーネントでこれらのプロパティを設定できます。設定されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、以下を参照してください。  
  
    > [!NOTE]
    >  上記のコンテキスト プロパティのセットのいずれかが昇格されていて、それらのコンテキスト プロパティに関連付けられたアグリーメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で見つけることができない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってメッセージが中断されます。  
    >   
    >  ユーザーが意図的にアグリーメント解決用のコンテキスト プロパティのセットを記述し、リゾルバーが OnewayAgreement を識別できない場合は、メッセージが中断されます。 コンテキスト プロパティのセットに基づいてアグリーメントを解決できない場合、そのことを示す警告メッセージが EventLog にスローされます。  
  
5.  手順 4 が成功しない、または昇格前のコンテキスト プロパティのいずれも、EDI メッセージがアグリーメントに解決アグリーメントに関連付けられている送信ポートとメッセージをサブスクライブした送信ポートを照合することによってです。  
  
    > [!NOTE]
    >  1 つの送信ポートが複数のアグリーメントに関連付けられていると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエラーが生成されます。  
  
6.  手順 1.、2.、3.、または 4. でアグリーメントが見つからない場合、送信パイプラインはフォールバック アグリーメント設定を使用して、送信メッセージを生成します。  
  
 **送信者と受信者のコンテキスト プロパティ照合によるアグリーメントの解決**  
  
 前の 2 番目の手順で、照合に使用されたコンテキスト プロパティは EDI.DestinationPartySenderIdentifier、EDI.DestinationPartySenderQualifier、EDI.DestinationPartyReceiverIdentifier、および EDI.DestinationPartyReceiverQualifier の 4 つです。 これらのコンテキスト プロパティの名前空間は、`http://schemas.microsoft.com/Edi/PropertySchema` です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、これらの値と、一方向のアグリーメント プロパティ内の関連する送信者および受信者の識別子および修飾子との照合を試みます。 これらのフィールドは ISA05、ISA06、ISA07、および ISA08 x12 の場合、**識別子**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスです edifact の場合、これらのフィールドは、UNB2.1、UNB2.2、。UNB3.1、および unb3.2 で、**識別子**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 送信者と受信者の識別子および修飾子の 4 つすべてを使用して送信側アグリーメントの解決を有効にするには、これらの 4 つのコンテキスト プロパティをすべて設定する必要があります。 この操作により、アグリーメントが一意に識別されます。 アグリーメント参照についてこの方法を使用することで、送信側の処理の柔軟性が高まります。 たとえば、この方法を使用すると、場合によっては複数の送信ポートを作成する必要がなくなり、送信ポート フィルターが複雑にならないようにすることができます。 また、必要に応じて、OneWayAgreementId プロパティの設定を回避できます。  
  
 あるメッセージに 4 つのコンテキスト プロパティがすべて設定されている場合で、これらのコンテキスト プロパティとこのプロパティの間に一致が見られないときは、そのメッセージは中断されます。 アグリーメントは、4 つのすべてのコンテキスト プロパティが設定されていない場合にのみ、アグリーメントに関連付けられた送信ポートを使用して解決されます。  
  
> [!NOTE]
>  EDI パイプライン内のメッセージは、有効な状態のアグリーメントに解決されるまで、アグリーメント解決における次の手順に進みます。 たとえば、メッセージがアグリーメント解決の最初の手順で解決されたとしても、アグリーメントが無効な状態の場合、メッセージは次の解決手順に進みます。  
  
## <a name="schema-determination"></a>スキーマの決定  
 EDI 送信パイプラインは、各トランザクション セットの中間 XML ファイル (ドキュメントの種類情報またはルート ノード内) に含まれているスキーマ名とスキーマ名前空間から作成されるメッセージに適用するスキーマを決定します。  
  
 保存されているインターチェンジの場合、送信パイプラインは、中間 XML ファイルの個々のトランザクション セットにあるドキュメントの種類情報を使用して完全なインターチェンジを作成します。 エンベロープ セグメントの処理には、制御セグメントのスキーマが使用されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)