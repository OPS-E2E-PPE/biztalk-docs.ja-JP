---
title: GetContextProperty2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f834bf1271f6706c332123d8b1835e0bd730f069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246146"
---
# <a name="getcontextproperty"></a>GetContextProperty
要求されたコンテキスト プロパティをスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>パラメーター  
 次のコンテキスト プロパティ名のいずれかを指定します。  
  
|コンテキスト プロパティ名|Description|  
|---------------------------|-----------------|  
|EventTime|現在の日付と時刻です。|  
|InstanceId|ワークフロー インスタンスの ID です。|  
  
> [!NOTE]
>  コンテキスト プロパティ名は大文字と小文字が区別されます。  
  
## <a name="pushed-value"></a>プッシュされた値  
 要求されたコンテキスト プロパティを表す文字列です。  
  
## <a name="remarks"></a>解説  
 時刻は UTC 形式でデータベース内部に格納されます。  
  
## <a name="example"></a>例  
 次の例では、式をプルするために、 **InstanceId**相関 ID を設定する correlationID ブロックの内部で使用します。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 これは `GetContextProperty` の一般的な使用方法です。