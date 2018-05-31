---
title: Find メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5432c68c36dcf8e769351af6d57f3cd3ed712b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245970"
---
# <a name="find-method"></a>Find メソッド
指定された部分検索キーに合致するキーの一覧を返すために使用します。 インスタンスが 1 つだけしかないコンポーネント インターフェイスの場合、つまりキーが存在しない場合、`Find()` 関数は生成されません。 関連項目[Get メソッド](../core/get-method.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`partialKey`|個々のキーが任意の場合の構造。|  
|`keyList`|`partialKey` と一致するキーのリスト。 これは、出力パラメーターです。<br /><br /> 特定のコンポーネント インターフェイスについて定義された Find Keys のセットに対応するキー。|  
  
## <a name="remarks"></a>解説  
 部分キーを指定する場合、PeopleSoft 内部の `Find()` 関数の場合と同じワイルドカード検索を使用することができます。 たとえば、"11" という部分 ACCOUNT キーは "11" で始まるすべての ACCOUNT キーを返し、"%40" の場合はキー内に "40" が含まれるすべての ACCOUNT キーを返します。 "_4_4" という部分キーは、2 文字目と 4 文字目に "4" という文字が含まれるすべての ACCOUNT キーを返します。  
  
 注: PeopleSoft Server の現在の実装で 300 を超える項目が検索条件に一致する場合、呼び出しは失敗します。 これは、PeopleSoft Server の制限です。 Microsoft BizTalk Adapter for PeopleSoft Enterprise の `Find()` メソッドは、コンポーネント インターフェイスに含まれる PeopleSoft の `Find` 関数が有効で、Get キーが利用できる場合に提供されます。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)