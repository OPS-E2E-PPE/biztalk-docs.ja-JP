---
title: GetContextProperty2 | Microsoft Docs
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
ms.openlocfilehash: ec2f155b9fdb1cf79419531cc7ec2d3e8b87c791
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387699"
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
  
|コンテキスト プロパティ名|説明|  
|---------------------------|-----------------|  
|EventTime|現在の日付と時刻です。|  
|InstanceId|ワークフロー インスタンスの id。|  
  
> [!NOTE]
>  コンテキスト プロパティ名は大文字と小文字が区別されます。  
  
## <a name="pushed-value"></a>プッシュされた値  
 要求されたコンテキスト プロパティを表す文字列です。  
  
## <a name="remarks"></a>コメント  
 時刻は UTC 形式でデータベース内部に格納されます。  
  
## <a name="example"></a>例  
 取得する式は、次の例で、 **InstanceId**相関 ID を設定する correlationID ブロックの内部で使用  
  
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