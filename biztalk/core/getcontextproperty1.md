---
title: GetContextProperty1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e843a8324526e183a577425a015b49c7be3725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345125"
---
# <a name="getcontextproperty"></a>GetContextProperty
要求されたコンテキスト プロパティをスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>パラメーター  
 次のコンテキスト プロパティ名のいずれかを指定します。  
  
|コンテキスト プロパティ名|説明|  
|---------------------------|-----------------|  
|EventTime|現在の日付と時刻です。|  
|SessionId|ワークフロー セッション ID です。|  
  
> [!NOTE]
>  コンテキスト プロパティ名は大文字と小文字が区別されます。  
  
## <a name="pushed-value"></a>プッシュされた値  
 要求されたコンテキスト プロパティを表す文字列です。  
  
## <a name="remarks"></a>コメント  
 時刻は UTC 形式でデータベース内部に格納されます。  
  
## <a name="example"></a>例  
 次に示す更新された式の例では、現在のイベントの時刻を取得することで、承認日を取得します。  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 これは `GetContextProperty` の一般的な使用方法です。  
  
## <a name="see-also"></a>参照  
 [Windows Communication Foundation での操作](../core/operations-in-windows-communication-foundation.md)