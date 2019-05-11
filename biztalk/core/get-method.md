---
title: メソッドの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fbf3b80fce70cac1ac95d21c143cdb64fae6305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345140"
---
# <a name="get-method"></a>Get メソッド
入力キー パラメーター (key1、key2、... に基づいてプロパティを取得するために使用 keyn)。 出力パラメーターは、キーのパラメーターに一致するレコードのプロパティを含む構造です。 コンポーネント インターフェイスに 1 つだけのインスタンスがある場合 (つまりはキー)、Get 関数にキー パラメーターが含まれていません。 参照してください[Find メソッド](../core/find-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`key`|一連のパラメーター、サーバー データベースに存在する必要があります。それ以外の場合、エラーが発生します。 これらのキーは、特定のコンポーネント インターフェイスで定義されている一連の Get キーに対応します。|  
|`properties`|呼び出しの完了時に返されるコンポーネント インターフェイスのプロパティの完全な構造が含まれています。|  
|`getHistoryItems`|ブール値です。 コンポーネント インターフェイスのプロパティが、effective-dated 項目レベル 0 未満 (と名前が EFFDT のキー フィールド) を含めることがかどうか、`getHistoryItems`追加のパラメーターが必要です。<br /><br /> 値の場合。<br /><br /> -True-すべての有効日が指定された項目が (任意のレベルで埋め込むでした) ことがシーケンスとして返されます。 過去の有効日が指定された項目、現在の有効日が指定された項目だけでなく今後すべての有効日が指定された項目すべてが含まれます<br />-False-のみ現在と未来の有効日が指定された項目が返されます。 同じインスタンスで更新する後続の呼び出しが行われます、し`getHistoryItems`を False に設定する必要があります。|  
  
### <a name="remarks"></a>コメント  
 コンポーネント インターフェイスのプロパティには、有効な日付が含まれている場合の項目レベル (つまり、キー フィールドの名前が EFFDT の)、0 未満、追加のパラメーター`getHistoryItems`が必要です。 このパラメーターはブール型です。 True に設定されている場合は、すべての有効日が指定された項目が (任意のレベルで埋め込むでした) ことがシーケンスとして返されます。 過去の有効日が指定された項目、現在の有効日が指定された項目だけでなく今後すべての有効日が指定された項目すべてが含まれます。 場合、`getHistoryItems`パラメーターは、False に設定されて、のみ、現在と未来の有効日が指定された項目が返されます。 同じインスタンスで更新する後続の呼び出しがし、作成される場合`getHistoryItems`を False に設定する必要があります。 参照してください[UpdateEx メソッド](../core/updateex-method.md)します。  
  
 コンポーネント インターフェイスが 1 つだけのインスタンスが存在できるケースのように、キーを持たない場合、`Get()`メソッドの形式。  
  
```  
Get(properties)  
```  
  
 有効日が指定された項目の詳細については、PeopleSoft Enterprise のドキュメントを参照してください。  
  
> [!NOTE]
>  BizTalk Adapter for PeopleSoft Enterprise`Get()`メソッドが提供される場合、PeopleSoft`Get`コンポーネント インターフェイスで機能を有効にします。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)