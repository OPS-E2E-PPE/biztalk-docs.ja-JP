---
title: GetContextProperty1 |Microsoft ドキュメント
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
ms.openlocfilehash: 65b7ffffe4b21e3317b920ac50cdc27b12d708d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246266"
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
  
|コンテキスト プロパティ名|Description|  
|---------------------------|-----------------|  
|EventTime|現在の日付と時刻です。|  
|SessionId|ワークフロー セッション ID です。|  
  
> [!NOTE]
>  コンテキスト プロパティ名は大文字と小文字が区別されます。  
  
## <a name="pushed-value"></a>プッシュされた値  
 要求されたコンテキスト プロパティを表す文字列です。  
  
## <a name="remarks"></a>解説  
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