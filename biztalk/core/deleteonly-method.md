---
title: DeleteOnly メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3982c67b4c2eb572a57a4ad602b1d302f9b53ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239722"
---
# <a name="deleteonly-method"></a>DeleteOnly メソッド
コレクション内のアイテムを削除できます。  
  
## <a name="syntax"></a>構文  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`key`|指定する必要があるパラメーター セットです。 このキー セットはサーバー データベースに存在する必要があります。存在しない場合、エラーが発生します。 これらのキーは、特定のコンポーネント インターフェイスに定義された一連の Get キーに対応します。|  
|`correctionMode`|ブール型のフラグ。 true に設定すると、コレクションの有効日が過去になったアイテムを削除できます。 具体的には、EFFDT が現在の有効日より前になっているアイテムを削除できます。 このフラグを TRUE に設定しない場合、これらの項目への変更により、PeopleSoft サーバーからエラーが返されます。 **注:** 、`correctionMode`引数は、effective-dated 項目を含むコンポーネント インターフェイスに対してのみ公開されます。 それ以外の場合、引数の一部としては表示されません。|  
|`interactiveMode`|エラー処理に使用されます。<br /><br /> コンポーネント インターフェイスでプロパティにアクセスする場合、BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft から提供されている API を使用してコンポーネント インターフェイス内の個々のフィールドを読み書きします。ただし、これらの変更は一度に 1 つずつ PeopleSoft サーバーに伝達されるわけではありません。 代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と対話) が、すべての変更を 1 つのパッケージにしてサーバーに送信します。 個別の更新が失敗した場合、汎用エラーが返されます。このエラーは、実際のエラーを特定しません。 対話モードを TRUE に設定することで、すべてのフィールド更新がサーバーに個別に送信されます。 これによってパフォーマンスに大きな影響が及びますが、更新が失敗した場合 (たとえば、フィールドの設定に無効な値が使用された場合) には、具体的なエラー情報が提供されます。<br /><br /> `interactiveMode` パラメーターを使用すると、パフォーマンスを最大限に発揮し、フィールド更新レベルでエラーが報告されます。 この機能を適切に使用するには、`interactiveMode` を FALSE に設定して通常の呼び出しを行うことをお勧めします。 パフォーマンスへの影響はありません。 エラーが返された場合は、interactiveMode フラグを TRUE に設定して同じ呼び出しを再試行できます。 呼び出しが失敗した場合、サーバーはより正確なエラー メッセージを返します。|  
|`properties`|サーバーに存在する構造のサブセットが入ります。 リーフであるアイテムはすべて削除されます。|  
  
## <a name="remarks"></a>解説  
 プロパティのデータ型はコンポーネント インターフェイスの `CreateEx` メソッドまたは `UpdateEx` メソッドと同じです。ただし、キー値のみが重要です。 キー以外の値は無視されます。 キー値はサーバーのキー値と一致する必要があります。一致しない場合、例外が発生します。  
  
 次に、キー値の使用方法を示します。 コレクションに次のアイテムがあるとします。  
  
-   item0  
  
-   item1  
  
-   item2  
  
-   item3  
  
 プロパティの item1 と item3 のキーを指定すると、item1 と item3 を削除できます。  
  
-   item1  
  
-   item3  
  
 呼び出し後、サーバーのコレクションには次のアイテムが残ります。  
  
-   item0  
  
-   item2  
  
 2 番目の例では、他のコレクションが入ったアイテムを示します。  
  
-   item0  
  
    -   item0a  
  
-   item1  
  
    -   item1a  
  
    -   item1b  
  
    -   item1c  
  
-   item2  
  
    -   item2a  
  
    -   item2b  
  
 item1b と item2 へのキーを指定することで item1b とすべての item2 を削除できます。  
  
-   item1  
  
    -   item1b  
  
-   item2  
  
 item2 の空のサブコレクションを指定することで、item2 をリーフにし、そのサブブランチ全体が削除されます。 呼び出し後、サーバーには次のアイテムが残ります。  
  
-   item0  
  
    -   item0a  
  
-   item1  
  
    -   item1a  
  
    -   item1c  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)