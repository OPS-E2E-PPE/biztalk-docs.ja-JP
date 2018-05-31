---
title: Get メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: d56b060cc261f707a4aa7b0d6a496a62707c4dca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246522"
---
# <a name="get-method"></a>Get メソッド
入力キー パラメーター (key1、key2、... に基づいてプロパティを取得するために使用 keyn)。 出力パラメーターは、キー パラメーターに一致するレコードのプロパティを含む構造です。 コンポーネント インターフェイスのインスタンスが 1 つしかない場合 (キーがない場合) は、Get 関数にキー パラメーターは含まれません。 参照してください[Find メソッド](../core/find-method.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`key`|このパラメーターのセットがサーバー データベースに存在する必要があります。存在しない場合、エラーが発生します。 これらのキーは、特定のコンポーネント インターフェイスに定義されているキーの取得のセットと対応します。|  
|`properties`|呼び出しの完了時に返されるコンポーネント インターフェイスのプロパティの完全な構造が含まれます。|  
|`getHistoryItems`|ブール値です。 コンポーネント インターフェイスのプロパティにレベル 0 未満の有効日が指定された項目 (名前が EFFDT のキー フィールド) が含まれている場合は、追加のパラメーターとして `getHistoryItems` を指定する必要があります。<br /><br /> 値の場合。<br /><br /> -True、すべての有効日が指定された項目が (任意のレベルで埋め込むことができます) をシーケンスとして返されます。 これには、過去の有効日が指定された項目、現在の有効日が指定された項目、および未来の有効日が指定された項目のすべてが含まれます。<br />-False: 現在のおよび未来の有効日が指定された項目が返されます。 同じインスタンス上の更新の後続の呼び出しになります、し`getHistoryItems`False に設定する必要があります。|  
  
### <a name="remarks"></a>解説  
 コンポーネント インターフェイスのプロパティに有効日が含まれている場合アイテム レベル 0 (つまり、キー フィールドで名前が EFFDT の)、追加のパラメーター`getHistoryItems`が必要です。 このパラメーターはブール型です。 このパラメーターを True に設定すると、有効日が指定されたすべての項目がシーケンスとして返されます (任意のレベルで埋め込むことができます)。 過去の未来の有効日が指定された項目だけでなく、有効日が指定された項目、現在の有効日が指定された項目すべてが含まれます。 `getHistoryItems` パラメーターを False に設定すると、現在または未来の有効日が指定された項目のみが返されます。 同じインスタンスで続けて更新の呼び出しを行う場合は、`getHistoryItems` を False に設定する必要があります。 関連項目[UpdateEx メソッド](../core/updateex-method.md)です。  
  
 コンポーネント インターフェイスにキーがない場合 (インスタンスが 1 つしかない場合)、`Get()` メソッドの形式は次のようになります。  
  
```  
Get(properties)  
```  
  
 有効日が指定された項目の詳細については、PeopleSoft Enterprise のドキュメントを参照してください。  
  
> [!NOTE]
>  コンポーネント インターフェイスで PeopleSoft の `Get()` 関数が有効な場合、BizTalk Adapter for PeopleSoft Enterprise `Get` メソッドが提供されます。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)