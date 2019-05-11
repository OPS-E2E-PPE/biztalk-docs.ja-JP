---
title: Find メソッド |Microsoft Docs
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
ms.openlocfilehash: 81599a87a88aaa383616653435119ec95d6ff430
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345386"
---
# <a name="find-method"></a>Find メソッド
指定された部分検索キーに合致するキーの一覧を取得するために使用します。 インスタンスを 1 つだけ持つコンポーネント インターフェイス、つまりがないこと、キーに注意してください、`Find()`関数は生成されません。 参照してください[Get メソッド](../core/get-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`partialKey`|個々 のキーが省略可能な構造体。|  
|`keyList`|一致するキーの一覧、`partialKey`します。 これは、出力パラメーターです。<br /><br /> キーは、特定のコンポーネント インターフェイスに定義された Find Keys のセットに対応します。|  
  
## <a name="remarks"></a>コメント  
 部分キーを指定すると、PeopleSoft 内部の同じワイルドカード検索を使用することは`Find()`関数。 たとえば、「11」の部分のアカウント キーは「11」で始まるすべてのアカウント キーを返しますの一方"40"が、キーの任意の場所にある「40」が含まれているすべてのアカウント キーを返します。 部分キー「_4_4」は、2 番目と 4 番目の位置に文字「4」ですべてのアカウント キーを返します。  
  
 注:PeopleSoft Server の現在の実装で 300 を超える項目が、検索条件に一致する場合は、呼び出しが失敗します。 これは、PeopleSoft server の制限です。 Microsoft BizTalk Adapter for PeopleSoft Enterprise`Find()`メソッドが提供される場合、PeopleSoft`Find`コンポーネント インターフェイスで関数が有効になっており、Get キーが提供されます。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)