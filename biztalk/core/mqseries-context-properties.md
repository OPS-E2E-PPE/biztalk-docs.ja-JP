---
title: MQSeries コンテキスト プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQCIH_TaskEndStatus property [MQSeries adapters]
- MQIIH_SecurityScope property [MQSeries adapters]
- MQCIH_AbendCode property [MQSeries adapters]
- filters, MQSeries adapters
- MQCIH_ReturnCode property [MQSeries adapters]
- MQCIH_TransactionId property [MQSeries adapters]
- MQCIH_ReplyToFormat property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- MQMD_PutTime property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQMD_PutApplName property [MQSeries adapters]
- configuring [MQSeries adapters], filtering
- MQCIH_UOWControl property [MQSeries adapters]
- MQCIH_ErrorOffset property [MQSeries adapters]
- MQMD_Priority property [MQSeries adapters]
- MQMD_MsgSeqNumber property [MQSeries adapters]
- MQMD_Format property [MQSeries adapters]
- MQCIH_ConversationalTask property [MQSeries adapters]
- Message Descriptor table [MQSeries adapters]
- MQMD_Feedback property [MQSeries adapters]
- MQCIH_Authenticator property [MQSeries adapters]
- MQIIH_TranState property [MQSeries adapters]
- MQCIH_AttentionId property [MQSeries adapters]
- MQMD_UserIdentifier property [MQSeries adapters]
- MQCIH_Flags property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQIIH_Format property [MQSeries adapters]
- MQMD_Offset property [MQSeries adapters]
- MQMD_BackoutCount property [MQSeries adapters]
- MQMD_Report property [MQSeries adapters]
- MQMD_MsgFlags property [MQSeries adapters]
- MQSeries adapters, filtering
- MQMD_ApplIdentityData property [MQSeries adapters]
- MQIIH_Authenticator property [MQSeries adapters]
- MQIIH_MFSMapName property [MQSeries adapters]
- MQCIH_LinkType property [MQSeries adapters]
- MQMD_Persistence property [MQSeries adapters]
- MQCIH_CursorPosition property [MQSeries adapters]
- MQCIH_Format property [MQSeries adapters]
- MQCIH_Facility property [MQSeries adapters]
- MQCIH_CancelCode property [MQSeries adapters]
- MQMD_PutDate property [MQSeries adapters]
- MQCIH_NextTransactionId property [MQSeries adapters]
- MQIIH_CommitMode property [MQSeries adapters]
- MQIIH_ReplyToFormat property [MQSeries adapters]
- MQCIH_Function property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- MQCIH_StartCode property [MQSeries adapters]
- MQMD_Expiry property [MQSeries adapters]
- MQMD_PutApplType property [MQSeries adapters]
- MQCIH_FacilityLike property [MQSeries adapters]
- MQIIH_Flags property [MQSeries adapters]
- MQCIH_CompCode property [MQSeries adapters]
- MQSeries adapters, properties
- MQCIH_FacilityKeepTime property [MQSeries adapters]
- MQMD_ApplOriginData property [MQSeries adapters]
- MQCIH_Reason property [MQSeries adapters]
- MQIIH_LTermOverride property [MQSeries adapters]
- MQMD_CodedCharSetId property [MQSeries adapters]
- MQMD_GroupID property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgType property [MQSeries adapters]
- MQMD_OriginalLength property [MQSeries adapters]
- MQMD_Encoding property [MQSeries adapters]
- MQMD_AccountingToken property [MQSeries adapters]
- MQCIH_OutputDataLength property [MQSeries adapters]
- MQIIH_TranInstanceId property [MQSeries adapters]
- MQCIH_GetWaitInterval property [MQSeries adapters]
- MQCIH_ADSDescriptor property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: 1b22b7d7-432b-4ec5-938c-c43077ce3e0f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27309379fac2c4821251f27fd2aa5a6e9d59418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266626"
---
# <a name="mqseries-context-properties"></a>MQSeries コンテキスト プロパティ
MQSeries アダプタには、アプリケーションで使用できる、MQSeries に固有のコンテキスト プロパティ セットが用意されています。 これらのプロパティは、フィルタ式やオーケストレーションで使用できます。  
  
 MQSeries アダプタにバインドされた送信ポートに送信するメッセージに MQSeries コンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用し、MQSeries 名前空間の使用可能ないずれかのコンテキスト プロパティを指定します。  
  
 MQSeries を設定する例を次に示します**MQMD_UserIdentifier**プロパティ。  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 IBM MQSeries SDK に同梱されている、C プログラミング言語のヘッダー ファイルから列挙値を取得する必要があります。 これらのファイルは、Program Files\IBM\WebSphere MQ\Tools\c\include フォルダにあり、 MQSeries コンテキスト プロパティ値の設定または読み取りを行うときに使用する値が定義されています。  
  
 16 進数文字列値は、バイナリ値を表す文字列です。 これらの文字列値に 0x などのプレフィックスは付いていません。 0 ～ 9 の数字と、a ～ f、または A ～ F の文字が含まれています。 MQSeries アダプタでは、スペースは無視されます。  
  
 これらのプロパティの詳細については、IBM WebSphere MQ のドキュメントを参照してください。  
  
 次の表は、使用可能なメッセージ記述子 (MQMD 構造) プロパティの完全なセットと、それらに対応する型と値を示しています。  
  
|名前|型|長さ|値|  
|----------|----------|------------|-----------|  
|**MQMD_AccountingToken**|string|64|16 進数文字列|  
|**MQMD_ApplIdentityData**|string|32|16 進数文字列|  
|**MQMD_ApplOriginData**|string|4|文字列<br /><br /> **既定値:** 領域|  
|**MQMD_BackoutCount**|unsigned int|4|数値<br /><br /> 読み取り専用<br /><br /> **既定値:** 0|  
|**MQMD_CodedCharSetId**|unsigned int|4|数値<br /><br /> **既定値:** 0|  
|**MQMD_CorrelId**|string|48|16 進数文字列|  
|**MQMD_Encoding**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。 **既定値:** 0|  
|**MQMD_Expiry**|unsigned int|4|数値|  
|**MQMD_Feedback**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。 **既定値:** 0|  
|**MQMD_Format**|string|8|文字列<br /><br /> MQXMIT に設定した場合、MQXQH プロパティに値が設定されていることを確認してください。|  
|**MQMD_GroupID**|string|48|16 進数文字列|  
|**MQMD_MsgFlags**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。 **既定値:** 0|  
|**MQMD_MsgId**|string|48|16 進数文字列|  
|**MQMD_MsgSeqNumber**|unsigned int|4||  
|**MQMD_MsgType**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。|  
|**MQMD_Offset**|unsigned int|4||  
|**MQMD_OriginalLength**|unsigned int|4||  
|**MQMD_Persistence**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。|  
|**MQMD_Priority**|unsigned int|4|数値|  
|**MQMD_PutApplName**|string|28|文字列<br /><br /> **既定値:** 領域|  
|**MQMD_PutApplType**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。 **既定値:** 0|  
|**MQMD_PutDate**|string|8|日付|  
|**MQMD_PutTime**|string|8|[時刻]|  
|**MQMD_ReplyToQ**|string|48|文字列<br /><br /> **既定値:** 領域|  
|**MQMD_ReplyToQMgr**|string|48|文字列<br /><br /> **既定値:** 領域|  
|**MQMD_Report**|unsigned int|4|数値<br /><br /> ヘッダー ファイルの値を使用します。|  
|**MQMD_UserIdentifier**|string|12|文字列<br /><br /> 使用するときに、ユーザーの識別子を含む、 **SSOAffiliateApplication**プロパティです。|  
  
 MQSeries 転送キューから直接メッセージを受信するとき、MQSeries アダプタでは、転送キューのヘッダー プロパティ (MQXQH データ構造) をフォーマットし、それらを対応するコンテキスト プロパティに配置します。 ヘッダーのプロパティはフォーマットされ、対応するコンテキスト プロパティ場合にのみから値を割り当てられているメッセージを MQSeries 転送キューに直接送信するときに、 **MQMD_Format** MQXMIT の値を持つプロパティです。 次の表では、ヘッダー プロパティについて説明します。  
  
|名前|型|長さ|値|  
|----------|----------|------------|-----------|  
|**MQXQH_RemoteQMgrName**|string|48|string|  
|**MQXQH_RemoteQName**|string|48|string|  
  
 ここまで記載したプロパティに加えて、アダプタでは、同じ規則に従って次のメッセージ記述子の値を作成します。 アダプタによってこれらのプロパティ名に付けられるプレフィックスは MQMD_ ではなく MQXQH_ ですが、それ以外の場合はこれらのプロパティ名が、メッセージ記述子テーブルで定義されているプロパティに直接マップされます。  
  
-   **MQXQH_MsgDesc_AccountingToken**  
  
-   **MQXQH_MsgDesc_ApplIdentityData**  
  
-   **MQXQH_MsgDesc_ApplOriginData**  
  
-   **MQXQH_MsgDesc_BackoutCount**  
  
-   **MQXQH_MsgDesc_CodedCharSetId**  
  
-   **MQXQH_MsgDesc_CorrelId**  
  
-   **MQXQH_MsgDesc_Encoding**  
  
-   **MQXQH_MsgDesc_Expiry**  
  
-   **MQXQH_MsgDesc_Feedback**  
  
-   **MQXQH_MsgDesc_Format**  
  
-   **MQXQH_MsgDesc_MsgId**  
  
-   **MQXQH_MsgDesc_MsgType**  
  
-   **MQXQH_MsgDesc_Persistence**  
  
-   **MQXQH_MsgDesc_Priority**  
  
-   **MQXQH_MsgDesc_PutApplName**  
  
-   **MQXQH_MsgDesc_PutApplType**  
  
-   **MQXQH_MsgDesc_PutDate**  
  
-   **MQXQH_MsgDesc_PutTime**  
  
-   **MQXQH_MsgDesc_ReplyToQ**  
  
-   **MQXQH_MsgDesc_ReplyToQMgr**  
  
-   **MQXQH_MsgDesc_Report**  
  
-   **MQXQH_MsgDesc_UserIdentifier**  
  
 プロパティ スキーマには、フィルタ式に使用できる MQSeries 関連のプロパティが他にも含まれています。 次の表は、これらのプロパティを示しています。  
  
|名前|型|長さ|値|  
|----------|----------|------------|-----------|  
|**MQCIH_AbendCode**|string|4||  
|**MQCIH_ADSDescriptor**|unsigned int|4||  
|**MQCIH_AttentionId**|string|4||  
|**MQCIH_Authenticator**|string|8|使用するときに、SSO パスワードに設定、 **SSOAffiliateApplication**プロパティです。 **注:** この値は、SSO パスワードの長さが 8 文字を超える場合、MQSeries アダプタによって空白に設定されます。|  
|**MQCIH_CancelCode**|string|4||  
|**MQCIH_CompCode**|unsigned int|4||  
|**MQCIH_ConversationalTask**|unsigned int|4||  
|**MQCIH_CursorPosition**|unsigned int|4||  
|**MQCIH_ErrorOffset**|unsigned int|4||  
|**MQCIH_Facility**|string|16|16 進数文字列|  
|**MQCIH_FacilityKeepTime**|unsigned int|4||  
|**MQCIH_FacilityLike**|string|4||  
|**MQCIH_Flags**|unsigned int|4||  
|**MQCIH_Format**|string|||  
|**MQCIH_Function**|string|4||  
|**MQCIH_GetWaitInterval**|unsigned int|4||  
|**MQCIH_LinkType**|unsigned int|4||  
|**MQCIH_NextTransactionId**|string|4||  
|**MQCIH_OutputDataLength**|unsigned int|4||  
|**MQCIH_Reason**|unsigned int|4||  
|**MQCIH_ReplyToFormat**|string|||  
|**MQCIH_ReturnCode**|unsigned int|4||  
|**MQCIH_StartCode**|string|4||  
|**MQCIH_TaskEndStatus**|unsigned int|4||  
|**MQCIH_TransactionId**|string|4||  
|**MQCIH_UOWControl**|unsigned int|4||  
|**MQIIH_Authenticator**|string|8|使用するときに、SSO パスワードに設定、 **SSOAffiliateApplication**プロパティです。 **注:** この値は、SSO パスワードの長さが 8 文字を超える場合、MQSeries アダプタによって空白に設定されます。|  
|**MQIIH_CommitMode**|string|||  
|**MQIIH_Flags**|unsigned int|4||  
|**MQIIH_Format**|string|||  
|**MQIIH_LTermOverride**|string|8||  
|**MQIIH_MFSMapName**|string|8||  
|**MQIIH_ReplyToFormat**|string|||  
|**MQIIH_SecurityScope**|string|||  
|**MQIIH_TranInstanceId**|string|32|16 進数文字列|  
|**MQIIH_TranState**|string|||  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)   
 [BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md)   
 [プロパティのデータ型の変換](../core/data-type-conversion-of-properties.md)