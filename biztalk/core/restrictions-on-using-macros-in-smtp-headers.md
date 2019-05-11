---
title: SMTP ヘッダーでのマクロの使用に関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- macros, SMTP headers [SMTP adapters]
- SMTP adapters, macros
- SMTP adapters, restrictions
- configuring [SMTP adapters], SMTP headers
- SMTP adapters, SMTP headers
- configuring [SMTP adapters], macros
- SMTP headers
ms.assetid: ceab0917-cb3c-423b-a15f-63747ab1d8da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03587ad44117d9bef9dbd14de4a4928f07f17592
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322005"
---
# <a name="restrictions-on-using-macros-in-smtp-headers"></a>SMTP ヘッダーでのマクロの使用に関する制限事項
定義済みのマクロを使用して、SMTP メッセージ ヘッダーの **Subject**、 **To**、 **From**、および **CC** プロパティを動的に形成できます。 メッセージを送信する前に、SMTP 送信ハンドラーによってヘッダー内のすべてのマクロが値に置き換えられます。 1 つのヘッダーを形成するときに、複数の異なるマクロを使用できます。  
  
 次のいずれかの条件に当てはまる場合、 **To**、 **From**、または **CC** ヘッダー内のマクロは SMTP 送信ハンドラーによって置き換えられません。  
  
- 対応するシステム プロパティが設定されていない場合  
  
- マクロのスペルが間違っている場合  
  
- マクロの値に、SMTP ヘッダーには無効な記号が含まれている場合  
  
  これらの条件が満たされた場合、SMTP 送信ハンドラーのリーフ マクロなどは<strong>%sourceparty%@somedomain.com</strong> または**from %sourceparty% メッセージ**します。  
  
  次の表に、 **To**、 **CC**、および **Subject** ヘッダーの形成に使用できるマクロを示します。  
  
|マクロ|説明|To での使用|CC での使用|Subject での使用|  
|-----------|-----------------|---------------------|---------------------|--------------------------|  
|%MessageID%|BizTalk Server 内のメッセージのグローバル一意識別子 (GUID)。 この値は、メッセージ コンテキスト プロパティ **BTS.MessageID**から取得されます。|いいえ|いいえ|はい|  
|%datetime_bts2000%|YYYYMMDDhhmmsss 形式の UTC 日時。sss は秒およびミリ秒を表します (たとえば、199707121035234 は 1997 年 7 月 12 日 10 時 35 分 23 秒 400 ミリ秒を表します)。|いいえ|いいえ|はい|  
|%datetime%|YYYY-MM-DDThhmmss 形式の UTC の日時 (例、1997-07-12T103508)。|いいえ|いいえ|はい|  
|%datetime.tz%|ローカルの日時に GMT のタイム ゾーンを加えた YYYY-MM-DDThhmmssTZD 形式の日時 (例、1997-07-12T103508+800)。|いいえ|いいえ|はい|  
|%time%|hhmmss 形式の UTC 時刻。|いいえ|いいえ|はい|  
|%time.tz%|ローカルの日付に GMT のタイム ゾーンを加えた hhmmssTZD 形式の日付 (例、124525+530)。|いいえ|いいえ|はい|  
|%SourceParty%|ファイル アダプタが受信したメッセージの受信元パーティの名前。|いいえ|いいえ|はい|  
|%SourcePartyQualifier%|ファイル アダプタが受信したメッセージの受信元パーティの修飾子。|いいえ|いいえ|はい|  
|%DestinationParty%|送信先パーティの名前。 この値は、メッセージ コンテキスト プロパティ **BTS.DestinationParty**から取得されます。|はい|[はい]|はい|  
|%DestinationPartyQualifier%|送信先パーティの修飾子。 この値は、メッセージ コンテキスト プロパティ **BTS.DestinationPartyQualifier**から取得されます。|いいえ|いいえ|はい|  
  
## <a name="see-also"></a>参照  
 [SMTP アダプター構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)