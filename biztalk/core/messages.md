---
title: メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e28c7296023cc9dec30dfede9c31f2de78e89dbd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394517"
---
# <a name="messages"></a>メッセージ
JMS メッセージのように、Enterprise Message Service (EMS) メッセージには、次の 3 つの独立したパーツが含まれています。 ヘッダー、プロパティ、および本文です。 ヘッダーでは、EMS メッセージの唯一の必須部分です。 このトピックでは、メッセージの処理方法には、Microsoft BizTalk Adapter for TIBCO Enterprise Message Service について説明します。  
  
> [!NOTE]
>  ヘッダー フィールドを取得または設定する (メッセージの優先度または関連付け ID は設定など) またはオーケストレーションからのメッセージ プロパティへの参照を追加する必要があります、 **Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll**で、プロジェクトがソリューション エクスプ ローラーを使用します。  
  
## <a name="message-header"></a>メッセージ ヘッダー  
 メッセージ ヘッダーには、一連値を含む定義済みのフィールドにはが含まれています。 BizTalk Adapter for TIBCO Enterprise Message Service を認識できること確認し、ヘッダーに設定することはできません。 アダプターをリダイレクトのプロパティで、値を設定または読み取り専用の値を設定しようとすると、{}セクション。  
  
### <a name="header-example"></a>ヘッダーの例  
 次の例では、**プロパティ = {先 = {String:queue [Q2]}}** します。 `Properties` 文字列を含むプロパティであり、文字列の内容は**Q2**します。 目的のセクションでは関係ありません。このセクションでは、ここで、アダプターで保持がように、移動できませんでした。 任意の場所、設定した値の文字列が含まれます。  
  
 `ReplyTo`最終的なコンシューマ応答を送信する場所をオーケストレーションのプロパティを設定できます。 EMS の設定、`Destination`プロパティ TIBCOEMS からメッセージを受信するとします。 この 2 番目のプロパティは読み取り専用では、TIBCOEMS からメッセージを受信するオーケストレーションと、オーケストレーションでは編集できません。  
  
 たとえば、オーケストレーションはメッセージをディスパッチし、オーケストレーション内で動的にリンク先を設定できません。 変換先の値は、メッセージを送信するポートが設定されます。  
  
 別のキューにメッセージをディスパッチする場合は、キューごとの送信ポートを作成する必要があります。 オーケストレーションは、メッセージの割り当てにどのポートを決定できます。  
  
 次のメッセージ例で、Destination =`{Queue[Q1]}`は読み取り専用です。 この値は、サーバーは、メッセージを受信するときに、TIBCOEMS によって設定されます。 変換先、Q1 は、の値は、トランスポートのプロパティに由来します。  
  
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
  
 ヘッダーには、一連オーケストレーションで使用するための BizTalk Server メッセージ コンテキストに昇格されて、値が含まれている定義済みのフィールドにはが含まれています。 昇格させたプロパティは、JMS 仕様および TIBCO Enterprise Message Service 拡張機能で定義されている標準のヘッダー プロパティに定義と同じです。 2 つを除くすべてのプロパティは EMS から受信すると、オーケストレーションに使用可能な:`Destination`と`ReplyTo`用に 1 つのプロパティとしてオーケストレーションで正しくマップできない変換先について説明します。  
  
 BizTalk Adapter for TIBCO EMS は、TIBCOEMS プロパティを文字列型にマップし、変換先の文字列表現を使用します。 次のようにこの`StaticQueue[queuename]`または`StatisTopic[topicname]`します。 オーケストレーションでの値を設定できます`ReplyTo`、し、アダプターがヘッダーに有効な変換先のオブジェクトで置き換えます。  
  
 アダプターは、オーケストレーションで使用できるすべての TIBCO EMS ヘッダー プロパティを記述するスキーマと参照アセンブリを提供します。 受信メッセージをフィルター処理または送信メッセージに追加する、これらのプロパティを使用できます。 オーケストレーションのフィルタの規則は、EMS サーバーのメッセージ セレクタのものとは異なります。 たとえば、オーケストレーションをフィルター処理できます、`TibcoEMS.ReplyTo`または`TibcoEMS.Destination`プロパティ、プロパティに基づくメッセージ セレクタを使用する JMS 仕様ではサポートされていませんが。  
  
 オーケストレーションでは、これらのプロパティが定義されている、ときに、JMS メッセージのヘッダー プロパティに含まれます。 また、EMS メッセージが受信したときに、これらのヘッダー プロパティは BizTalk Server のメッセージ コンテキストにコピーされます。  
  
 プロパティには、ポートの構成が一致すると、メッセージのプロパティの値は、ポートの構成にも優先されます。 たとえば、ポート、優先度が 4 に設定されて、オーケストレーションのロジックで 9 に、メッセージの優先順位を設定する場合、メッセージの受信、TIBCO EMS によって 9 の優先順位を持つものとして。  
  
### <a name="property-descriptions"></a>プロパティの説明  
 次の表では、TIBCO Enterprise Message Service の各プロパティは BizTalk アダプターで使用する方法について説明します。  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|TibcoEMS.MessageID|string|送信呼び出しでは、各メッセージに一意の ID を割り当てるし、ヘッダーに記録します。<br /><br /> すべてのメッセージ ID の値は、3 文字のプレフィックス ID (これは、この目的のため予約されています) を起動します。<br /><br /> 読み取り専用。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.Timestamp|long|ヘッダーに UTC タイムスタンプ呼び出しレコードを送信します。 これは、おおよその時間、サーバーがメッセージを受け入れることを示します。<br /><br /> 値が 1970 年 1 月 1 日以降はミリ秒単位<br /><br /> 読み取り専用。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.Redelivered|boolean|サーバーは、メッセージが前に配信されたメッセージを複製するかどうかを示すヘッダーを設定します。<br /><br /> -false-サーバーが、以前にコンシューマーに対してこのメッセージの配信は試行されません。<br />-true-可能性がありますが、保証されていないが、コンシューマーにこのメッセージを配信しようとして、サーバーが以前に、コンシューマーでは、適切な受信確認は返されませんでした。<br /><br /> 読み取り専用。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.Destination|string|このヘッダーで、メッセージの送信先 (キューまたはトピック) 呼び出しレコードを送信します。 形式は、適合変換先から文字列。 以前は、形式が説明します。<br /><br /> 読み取り専用。 値を変更しても、メッセージには影響しません。|  
|TibcoEMS.DeliveryMode|string|2 つの値があります。PERSISTENT と NON-PERSISTENT です。 既定値は、永続的なモードです。<br /><br /> アダプターは、BizTalk Server に送信されるメッセージの受信確認を行う前に、EMS サーバーからの受信確認を待機します。 このヘッダーのプロパティとポートの構成項目は、EMS は、アダプターにこの受信確認を送信し、メッセージ送信の信頼性の制御にかかる時間を制御します。<br /><br /> PERSISTENT 配信モードを使用して、EMS サーバーが、メッセージは、EMS サーバーで正常に保存するまでに待機します。 このアクションは、メッセージがキューに到着したことを保証します。 PERSISTENT モードの配信を使用する場合は、次を考慮してください。<br /><br /> メッセージが大きいほど、長く、送信されると、メッセージを考慮する BizTalk Server がかかります。<br /><br /> NON-PERSISTENT モードを使用して、EMS サーバーは、メッセージを保持する前に受信確認を返します。 エラーが、EMS サーバーで発生する場合は、BizTalk Server から正常に送信されたと見なされると、メッセージが失われます。|  
|TibcoEMS.Expiration|long|有効期限の前に、メッセージが存在する時間の長さ。 かどうかは 0 に設定すると、メッセージは期限切れになりません。<br /><br /> Time to live は、ミリ秒単位で指定されます。|  
|TibcoEMS.Priority|ssNoversion|通常、または優先としてメッセージの優先度を定義するのにには、順位付け、0 から 9 までの数値を使用します。 数字が大きくなるほど、優先順位が高い。|  
|TibcoEMS.CorrolationID|string|要求メッセージに応答メッセージのリンクなどのメッセージをリンクするために使用します。<br /><br /> これと同じ値は、通常、`EMS.JMSMessageID`します。 通常はと共に使用、`EMS.JMSReplyTo`プロパティ。|  
|TibcoEMS.ReplyTo|string|メッセージの返信を送信する宛先。 形式のと同じですが、`EMS.JMSDestination`とポートの構成もできます。|  
|TibcoEMS.Type|string|メッセージの種類 (テキスト、バイト、文字列など) については説明しません。<br /><br /> 一部の JMS プロバイダでは、メッセージ リポジトリを使用して、メッセージの種類の定義を格納します。 クライアント プログラムは、リポジトリ内の定義を参照するには、このフィールドに値を格納することができます。 EMS では、このヘッダーをサポートしますが、これを使用しません。<br /><br /> JMS 仕様では、標準のメッセージ定義リポジトリは定義しませんもはメッセージの種類の定義の名前付けポリシーを定義します。<br /><br /> 一部のプロバイダーでは、アプリケーション メッセージごとにメッセージの種類の定義が必要です。 このようなプロバイダーとの互換性を保証するためにクライアント プログラムは、クライアント アプリケーションがそれを使用しない場合でも、このヘッダーを設定できます。<br /><br /> 移植性を保証するためにクライアントは、(リテラル) ではなくシンボリック値では、このヘッダーを設定して、プロバイダのリポジトリに一致するように構成します。|  
  
## <a name="properties"></a>プロパティ  
 インテグレータは、JMS メッセージのプロパティの一部に、プロパティを追加するまで、BizTalk Server メッセージ コンテキストに昇格するプロパティのセットを定義できます。 インテグレータは、スキーマの作成中に、プロパティの型を定義するときに行われます。 メッセージ セレクタでこのプロパティの値を使用する場合、特定の操作は、プロパティの型に応じて有効です。 たとえば、メッセージ セレクタ**myMessageProperty > 5**は整数値として、プロパティを定義する必要があり、アダプターでは、値を整数値としてメッセージに使用すると、します。 昇格させるプロパティ、プロパティ名は、先頭が EMSX で始まる必要があります。 定義済みプロパティと同じ名前もありませんが、必要です。  
  
 BizTalk Adapter for TIBCO Enterprise Message Service は、このセクションに表示できる EMS 固有および JMS 固有のプロパティを宣言するスキーマと、アセンブリを提供します。 これらを拡張、除外を含めることができます。 メッセージのコンテキストで参照されるすべての EMSX プロパティは、EMS メッセージのメッセージ プロパティ セクションに格納されます。 詳細については、TIBCO EMS のユーザー ガイドを参照してください。  
  
## <a name="body"></a>本文  
 EMS は、JMS 仕様に列挙されたすべてのメッセージをサポートしています: テキスト、バイト、ストリーム、マップ、およびオブジェクト。 BizTalk Adapter for TIBCO EMS は、テキスト メッセージの種類のみをサポートします。  
  
 JMS では、テキスト タイプのメッセージが XML 形式の本文を含めることは必要ありません。 アダプターがメッセージの本文を処理しません提供されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信するとします。  そのため、BizTalk にアダプターによって送信されたメッセージ可能性がありますとして解析されない XML データ。  
  
## <a name="persistent-messages"></a>永続的なメッセージ  
 メッセージは、サブスクライバーに正確に 1 回限りの配信を保証するために、EMS サーバー上に保存することができます。ただし、アダプターのパフォーマンスに大きな影響を与えることがこのできます。 メッセージを送信するときに、EMS では、ローカル ストレージに、メッセージをアダプターにメッセージの受信確認の前に格納します。 ポートによって処理されるすべてのメッセージまたはオーケストレーションでは、メッセージごとに、このプロパティを設定することができます。  
  
 受信側の側面からないトピックにサブスクライブしている場合、アダプターがメッセージをミスすることができます。 サブスクリプションがない場合に、トピックに送信されたメッセージは、EMS では保持されません。 アダプターが現在サブスクライブしている; 場合でもメッセージへの投稿を受信するためのメカニズムただし、永続的なメッセージの使用と同様に、EMS のパフォーマンスに大きな影響を及ぼしますこれとは常に必要ありません。  
  
> [!NOTE]
>  EMS の観点から表示されるためのメカニズムが実装されていません。 またが、本当に必要な。 これはトピックでは、問題のみです。キューは影響しません。 トピックは通常使用時間に固有のデータ--株価情報、たとえばされます。 株式の価格が実行されなかった場合は、後でもう一度な投稿をされたわかります。  
  
 これらの理由から、ポートの構成に有効または、EMS サーバーでメッセージの永続性を無効にすることができます。  
  
## <a name="message-acknowledgement"></a>メッセージの受信確認  
 BizTalk Adapter for TIBCO Enterprise Message Service は、BizTalk Server にそのメッセージを適切にディスパッチするときに常に、メッセージの受信を確認します。 つまり、未確認のメッセージは、EMS からアダプタに再送信されます。 アダプターは、送信先自体; の設定ではこのため、メッセージが EMS によって再送信回数の合計を制御できません。ただし、かどうか、メッセージ ボックスに、メッセージが送信される場合、アダプターを制御できます。 EMS サーバーは、失敗したメッセージがキューに送信する最大回数を制御します。  
  
 再配信されるメッセージの場合、EMS サーバーの設定、`JMSRedelivered`プロパティを True に、インクリメント、`JMSXDeliveryCount`します。 両方のプロパティ値をオーケストレーションに利用できます。 配信せず、EMS の未配信キューにメッセージを移動することはできません。 これを行うと、メッセージのプロパティが変更されます。  
  
 メッセージには、その構成済みの最大再配信回数に達すると、EMS サーバーは、メッセージは削除されるか、$sys.undelivered キューに配置するかどうかを決定します。 EMS サーバーに基づく意思決定、`JMS_TIBCO_PRESERVE_UNDELIVERED`プロパティです。 場合 true の場合、はメッセージが未配信キューに、または削除されます。 このプロパティは、メッセージを送信する前に、オーケストレーションで設定できます。 配信後は、メッセージ プロパティを変更できません。 EMS に送信されるメッセージは BizTalk Server に受信確認が成功する場合。 EMS へのエラー送信テーマがある場合は中断されていて再試行可能に設定します。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)