---
title: "メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, headers
- messages, acknowledgements
- messages, persisting
- messages
- examples, message headers
- properties
- message headers
- EMS messages
ms.assetid: 65bb3431-7186-4d4c-b004-932cdf070e73
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f7313e93029ca75d345aa4e9603699c50399230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messages"></a>メッセージ
JMS メッセージのように、Enterprise Message Service (EMS) メッセージには、次の 3 つの別々 の部分が含まれています: ヘッダー、プロパティ、および本文です。 ヘッダーは、EMS メッセージで唯一の必須部分です。 ここでは、Microsoft BizTalk Adapter for TIBCO Enterprise Message Service でのメッセージの処理方法について説明します。  
  
> [!NOTE]
>  ヘッダー フィールドを取得または設定する (メッセージの優先度または関連付け ID は設定など) をオーケストレーションからのメッセージ プロパティへの参照を追加する必要があります、 **Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll**で、プロジェクトがソリューション エクスプ ローラーを使用します。  
  
## <a name="message-header"></a>メッセージ ヘッダー  
 メッセージ ヘッダーには、値が格納された、一連の定義済みフィールドがあります。 BizTalk Adapter for TIBCO Enterprise Message Service は、ヘッダーに設定できる値と設定できない値を認識しています。 読み取り専用の値を設定しようとすると、その値はリダイレクトされるか、Properties{} セクションに設定されます。  
  
### <a name="header-example"></a>ヘッダーの例  
 次の例でわかるように**プロパティ = {先 = {String:queue [Q2]}}**です。 `Properties`文字列を含むプロパティであり、文字列の内容は**Q2**です。 これは Destination セクションとは無関係です。Destination セクションには、ユーザーが設定した値が格納されています。この値は他のセクションには該当しないため、このセクションに保持されています。  
  
 オーケストレーションで `ReplyTo` プロパティを設定すると、応答の送信先となる最終的なコンシューマを指定できます。 TIBCOEMS からメッセージを受信すると、`Destination` プロパティが設定されます。 この 2 つ目のプロパティは、TIBCOEMS からメッセージを受信するオーケストレーションでは読み取り専用であり、編集できません。  
  
 たとえば、オーケストレーションでは、メッセージをディスパッチし、オーケストレーション内で送信先を動的に設定することはできません。 Destination の値は、メッセージの送信先のポートによって設定されます。  
  
 別のキューにメッセージをディスパッチする場合は、各キューの送信ポートを作成する必要があります。 これにより、オーケストレーションがメッセージの割り当て先のポートを決定できるようになります。  
  
 次のメッセージの例で、Destination= `{Queue[Q1]}` は読み取り専用です。 サーバーがメッセージを受信すると、TIBCOEMS によってこの値が設定されます。 Destination の値 Q1 は、トランスポートのプロパティから取得したものです。  
  
#### <a name="example"></a>例  
  
```  
TextMessage={   
    Header={ MessageID={ID:EMS-SERVER.824437A58B11C75F4:1}   
    Destination={Queue[Q1]}   
  
        ' This is READONLY. It gets set by the server when the  
        ' message is received by the server (EMS). It is set in the  
        ' Transport Properties when you specify that you want to  
        ' listen for messages on Q1.  
    ReplyTo={}   
    DeliveryMode={Persistent}   
    Redelivered={False}   
    CorrelationID={}   
    MsgType={}   
    Timestamp={12/1/2005 11:59:01 PM}   
    Expiration={0}   
    Priority={1} }   
    Properties={ Destination={String:Queue[Q2]} }   
  
        ' This is a property that contains a string, and the   
        ' contents of the string is Q2. This has nothing to do with  
        ' the Destination section above – it is just another   
        ' property that is set.   
        ' This is in the schema. The adapter knows what it can and   
        ' cannot set in an EMS header. The values that the adapter   
        ' cannot set are put in the Properties section.   
    text={<?xml version="1.0" encoding="utf-16"?>  
    <ns0:Employees xmlns:ns0="http://BizTalk_Server_Project1.Employee">  
        <Emp Id="Id_0">  
            Name>Name_0</Name>  
        </Emp>  
    </ns0:Employees>  
    }  
```  
  
 ヘッダーには、値が格納された、一連の定義済みフィールドがあり、これらの値が BizTalk Server のメッセージ コンテキストに昇格されて、オーケストレーションで使用できるようになります。 昇格されたプロパティは、JMS 仕様および TIBCO Enterprise Message Service 拡張で定義されている標準のヘッダー プロパティと定義上は同一です。 2 つを除くすべてのプロパティがオーケストレーション EMS から受信したとおりに使用可能な:`Destination`と`ReplyTo`を 1 つのプロパティとしてオーケストレーションで使用する適切にマップできない宛先を記述します。  
  
 BizTalk Adapter for TIBCO EMS では、TIBCOEMS プロパティを文字列型にマップし、送信先の文字列表記を使用します。 たとえば、`StaticQueue[queuename]` や `StatisTopic[topicname]` のようになります。 オーケストレーションで `ReplyTo` の値を設定できます。その場合、値がアダプタによって、ヘッダー内で有効な送信先オブジェクトに置き換えられます。  
  
 アダプタには、オーケストレーションで使用できるすべての TIBCO EMS ヘッダー プロパティを記述したスキーマおよび参照アセンブリが用意されています。 これらのプロパティは、受信メッセージのフィルタ処理と送信メッセージへの追加に使用できます。 オーケストレーションのフィルタを制御する規則は、EMS サーバーのメッセージ セレクタの規則とは異なります。 たとえば、オーケストレーションでは、`TibcoEMS.ReplyTo` プロパティまたは `TibcoEMS.Destination` プロパティに基づいてフィルタ処理できますが、JMS 仕様では、これらのプロパティに基づくメッセージ セレクタはサポートされません。  
  
 オーケストレーションでこれらのプロパティが定義されている場合は、JMS メッセージのヘッダー プロパティに組み込まれます。 また、EMS メッセージを受信したときは、これらのヘッダー プロパティが BizTalk Server のメッセージ コンテキストにコピーされます。  
  
 プロパティがポートの構成に一致した場合は、メッセージのプロパティの値が、ポートの構成よりも優先されます。 たとえば、ポートで優先度が 4 に設定されていても、オーケストレーションのロジックでメッセージの優先度を 9 に設定すると、TIBCO EMS では、優先度 9 としてメッセージが受信されます。  
  
### <a name="property-descriptions"></a>プロパティの説明  
 BizTalk Adapter for TIBCO Enterprise Message Service での各プロパティの用途を次の表に示します。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|TibcoEMS.MessageID|string|送信呼び出しが、各メッセージに一意の ID を割り当て、ヘッダーに記録します。<br /><br /> すべてのメッセージ ID の値は、この目的のために予約されている 3 文字のプレフィックス ID で始まります。<br /><br /> 読み取り専用です。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.Timestamp|long|送信呼び出しが、ヘッダーに UTC タイムスタンプを記録します。 これは、サーバーがメッセージを受け付けた時刻を示します。<br /><br /> 値は、1970 年 1 月 1 日からのミリ秒で示されます。<br /><br /> 読み取り専用です。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.Redelivered|boolean|サーバーは、メッセーが以前に配信されたメッセージを複製したものであるかどうかを示すためのヘッダーを設定します。次の値があります。<br /><br /> -false: サーバーが以前を試行していませんコンシューマーに対してこのメッセージを配信します。<br />場合は true。-可能性がありますが、信頼性は保証できませんが、コンシューマーに対してこのメッセージを配信しようとして、サーバーに以前が、コンシューマーでは、適切な受信確認は返されませんでした。<br /><br /> 読み取り専用です。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.Destination|string|送信呼び出しは、メッセージの送信先 (キューまたはトピック) をこのヘッダーに記録します。 形式は送信先から取得され、文字列に変換されます。 形式は前に説明した形式です。<br /><br /> 読み取り専用です。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.DeliveryMode|string|2 つの値を持つ: 永続的なと NON-PERSISTENT です。 既定値は PERSISTENT モードです。<br /><br /> アダプタは、EMS サーバーからの受信確認を待機してから、BizTalk Server にメッセージの受信確認を送信します。 このヘッダー プロパティとポートの構成アイテムは、この受信確認が EMS によってアダプタに送信されるまでの所定時間と、メッセージ送信の信頼性を制御します。<br /><br /> PERSISTENT 配信モードを使用すると、EMS サーバーは、メッセージが EMS サーバーに正常に保存されるまで待機します。 これにより、メッセージがキューに到着したことが確実になります。 PERSISTENT モードの配信を使用する場合は、以下を考慮してください。<br /><br /> メッセージの長さに比例して、BizTalk Server がメッセージが送信されたと見なすまでの時間が長くなります。<br /><br /> NON-PERSISTENT モードを使用すると、EMS サーバーは、メッセージが保存される前に受信確認を返します。 EMS サーバーでエラーが発生した場合は、メッセージが失われていても、BizTalk Server が、正常に送信されたと見なす可能性があります。|  
|TibcoEMS.Expiration|long|メッセージの有効期限が切れるまでの時間の長さです。 0 に設定すると、メッセージは期限切れになりません。<br /><br /> 有効期限はミリ秒単位で指定します。|  
|TibcoEMS.Priority|int|0 ～ 9 の数値による順位付けを使用して、メッセージの優先度が標準か、高いかを定義します。 数字が大きくなるほど、優先度は高くなります。|  
|TibcoEMS.CorrolationID|string|応答メッセージを要求メッセージに関連付けるなど、メッセージの関連付けに使用されます。<br /><br /> 通常は、`EMS.JMSMessageID` と同じ値です。 このプロパティは通常、`EMS.JMSReplyTo` プロパティと共に使用されます。|  
|TibcoEMS.ReplyTo|string|メッセージに対する返信の送信先です。 形式は、`EMS.JMSDestination` およびポートの構成と同じです。|  
|TibcoEMS.Type|string|メッセージの種類 (テキスト、バイト、文字列など) を示すものではありません。<br /><br /> 一部の JMS プロバイダは、メッセージ リポジトリに、メッセージの種類の定義を格納します。 クライアント プログラムでは、リポジトリ内の定義を参照するために、このフィールドに値を格納できます。 EMS では、このヘッダーがサポートされていますが、使用されることはありません。<br /><br /> JMS 仕様では、標準のメッセージ定義リポジトリは定義されていません。また、メッセージの種類の定義に関する名前付けポリシーも定義されていません。<br /><br /> プロバイダによっては、アプリケーション メッセージごとにメッセージの種類の定義が必要です。 クライアント プログラムでそのようなプロバイダとの互換性を確保するには、クライアント アプリケーションが使用しない場合でも、このヘッダーを設定します。<br /><br /> クライアントで移植性を確保するには、(リテラルではなく) シンボリック値を使用してこのヘッダーを設定し、プロバイダのリポジトリに適合するように構成します。|  
  
## <a name="properties"></a>[プロパティ]  
 インテグレータは、BizTalk Server のメッセージ コンテキストに昇格させるための一連のプロパティを定義できます。定義されたプロパティは、JMS メッセージのプロパティ部分に追加されます。 インテグレータは、スキーマの作成中に、慎重にプロパティの種類を定義します。 このプロパティの値がメッセージ セレクタで使用されると、プロパティの種類によっては、特定の操作が有効になります。 たとえば、メッセージ セレクタ**myMessageProperty > 5**はプロパティは、整数値として定義する必要があり、アダプターでは、値を整数値としてメッセージに使用される、します。 昇格させるプロパティは、プロパティ名の先頭が EMSX である必要があります。 定義済みのプロパティと同じ名前は使用できません。  
  
 BizTalk Adapter for TIBCO Enterprise Message Service には、このセクションに含めることができる EMS 固有および JMS 固有のプロパティを宣言するスキーマとアセンブリが用意されています。 これらを拡張して、除外を含めることができます。 メッセージ コンテキストで参照されているすべての EMSX プロパティは、EMS メッセージのメッセージ プロパティ セクションに書き込まれます。 詳細については、『TIBCO EMS Users Guide』を参照してください。  
  
## <a name="body"></a>本文  
 EMS は、JMS 仕様に列挙されたすべてのメッセージをサポートしています: テキスト、バイト、ストリーム、マップ、およびオブジェクト。 TIBCO EMS 用の BizTalk ではテキスト メッセージの種類のみをサポートしています。  
  
 JMS では、種類がテキストのメッセージに XML 形式の本文が含まれている必要はありません。 アダプターがメッセージの本文を処理しませんこれに用意されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信します。  したがって、BizTalk にアダプターによって送信されたメッセージ可能性がありますとして解析されない XML データです。  
  
## <a name="persistent-messages"></a>永続的なメッセージ  
 メッセージを EMS サーバーに保持すると、サブスクライバへの 1 回限りの配信を確実に行うことができますが、この方法はアダプタのパフォーマンスに大きな影響を与えます。 送信されたメッセージは、EMS のローカル ストアに格納され、その後でメッセージの受信確認がアダプタに送信されます。 このプロパティをオーケストレーション内でメッセージ単位で設定することも、すべてのメッセージがポートで処理されるように設定することもできます。  
  
 受信側の観点からは、アダプタがトピックにサブスクライブしていない場合、メッセージの受信に失敗する可能性があります。 サブスクリプションのないトピックに送信されたメッセージは、EMS で保持されません。 現在はサブスクライブされていない場合でも、送信されたメッセージを受信するためのメカニズムがアダプタに必要です。ただし、永続的なメッセージの使用と同様に、これも EMS のパフォーマンスに大きく影響し、常に必要というわけではありません。  
  
> [!NOTE]
>  EMS の観点からの受信メカニズムがありますが、実装されておらず、実際には推奨される方法ではありません。 これはトピックのみに関連する問題で、キューは影響を受けません。 トピックは通常、株式相場などの時間別のデータに使用されます。 株価を受信しなかった場合、通常は後で再送信されます。  
  
 このような理由から、ポートの構成で EMS サーバーでのメッセージの永続性を有効または無効にできます。  
  
## <a name="message-acknowledgement"></a>メッセージ受信確認  
 BizTalk Adapter for TIBCO Enterprise Message Service では、メッセージが BizTalk Server に適切にディスパッチされると、メッセージの受信確認が常に行われます。 したがって、未確認のメッセージは EMS からアダプタに再送信されます。 EMS からのメッセージの再送信回数は、送信先自体の構成であるため、アダプタでは制御できません。ただし、アダプタでは、メッセージがメッセージ ボックスに送信されるかどうかを制御できます。 EMS サーバーでは、失敗したメッセージがキューに送信される回数を制御します。  
  
 再配信されたメッセージについては、EMS サーバーが `JMSRedelivered` プロパティを True に設定し、`JMSXDeliveryCount` をインクリメントします。 両方のプロパティの値をオーケストレーションで利用できます。 メッセージを配信せずに、EMS の未配信キューに移動することはできません。 これを行うと、メッセージのプロパティが変わります。  
  
 最大再配信回数で設定されている回数に達すると、EMS サーバーにより、メッセージを削除するか、$sys.undelivered キューに書き込むかが決定されます。 EMS サーバーでは、`JMS_TIBCO_PRESERVE_UNDELIVERED` プロパティに基づいて、この決定を行います。True の場合はメッセージが未配信キューに書き込まれ、それ以外の場合は削除されます。 このプロパティは、メッセージの送信前にオーケストレーションで設定できます。 配信後は、メッセージのプロパティを変更できません。 EMS へのメッセージの送信が正常に完了すると、BizTalk Server に受信確認が送信されます。 EMS への送信中にエラーが発生すると、メッセージが中断され、再試行可能に設定されます。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)