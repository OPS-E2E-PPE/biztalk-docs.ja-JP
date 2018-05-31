---
title: UpdateEx メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UpdateEx method
ms.assetid: 2fa9c9cc-fd01-4765-8c31-facac188a19d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a6a64c6709eb9806612518c551372ba45d1a454
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287426"
---
# <a name="updateex-method"></a>UpdateEx メソッド
入力キー パラメーター (key1、key2、... に基づいてプロパティを更新するために使用 keyn)。 `UpdateEx` を使用する場合は、コレクション内のアイテムを削除できません。 削除には別のメソッドを使用します。 詳細については、次を参照してください。 [DeleteOnly メソッド](../core/deleteonly-method.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
UpdateEx (key1, key2, ... keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`key`|サーバー データベースに存在している必要があるパラメーターのセット。存在していない場合、エラーが発生します。 これらのキーは、特定のコンポーネント インターフェイスに定義された一連の Get キーに対応します。|  
|`correctionMode`|ブール型のフラグ。 True に設定すると、フィールド値を更新するか、コレクションに新しいアイテムを挿入することによって、有効日が指定されたアイテムを含むコンポーネント インターフェイスへの変更が許可されます。 具体的には、EFFDT が現在の有効日よりも前のアイテムに対する変更が許可されます。 このフラグを TRUE に設定しない場合、これらの項目への変更により、PeopleSoft サーバーからエラーが返されます。<br /><br /> `correctionMode` 引数は、effective-dated 項目を含むコンポーネント インターフェイスに対してのみ公開されます。 それ以外の場合は、引数の一部として表示されません。<br /><br /> 設定を避ける必要があります`correctionMode`を運用環境で TRUE にします。 (これはまた PeopleSoft からの勧告です。)過去の EFFDT キーで判別されるような、既に発生したイベントは変更しないでください。 これによって監査記録を作成できるようになります。 `UpdateEx` の `correctionMode` フラグを使用すると、この安全性のメカニズムを迂回することが可能になります。 アイテム内のフィールドを設定し、更新されたアイテムを (削除ではなく) 追加することによって、過去のイベントを非アクティブにすることをお勧めします。|  
|`interactiveMode`|エラー処理に使用されるフラグ。<br /><br /> BizTalk Adapter for PeopleSoft Enterprise が、コンポーネント インターフェイスに個々 のフィールドを読み書きする PeopleSoft が提供の Api を使用してコンポーネント インターフェイスでプロパティにアクセスするときにただし、これらの変更は、一度に 1 つずつ PeopleSoft サーバーに反映されませんされます。 代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise が操作する) がすべての変更をパッケージ化し、1 つのパッケージで変更をサーバーに送信します。 個別の更新が失敗した場合、汎用エラーが返されます。このエラーは、実際のエラーを特定しません。 対話モードを TRUE に設定することで、すべてのフィールド更新がサーバーに個別に送信されます。 これによってパフォーマンスに大きな影響が及びますが、更新が失敗した場合 (たとえば、フィールドの設定に無効な値が使用された場合) には、具体的なエラー情報が提供されます。<br /><br /> `interactiveMode` は最大のパフォーマンスを発揮し、フィールド更新レベルでエラーを報告します。 この機能を適切に使用するには、`interactiveMode` を FALSE に設定して通常の呼び出しを行うことをお勧めします。 パフォーマンスへの影響はありません。 エラーが返された場合は、`interactiveMode` フラグを TRUE に設定して、同じ呼び出しを再試行できます。 呼び出しが失敗した場合、サーバーはより正確なエラー メッセージを返します。|  
  
### <a name="remarks"></a>解説  
 この関数を呼び出す場合、キーに対応するレコードのプロパティが、入力パラメーターのプロパティに置き換えられます。 元のレコードを含むすべてのコレクションは削除され、入力パラメーターで指定されたものに置き換えられます。 これらのコレクションのサイズは一致している必要はありません。`UpdateEx` 内での手順が、既存のコレクション アイテムをすべて削除した後、指定されたコレクション アイテムを挿入するという手順であるからです。  
  
 コンポーネント インターフェイスのプロパティに有効日が指定されたアイテムが含まれている場合、元のリストは置き換えられるので、プロパティ パラメーターにすべての将来の有効日が指定されたアイテムが含まれている必要があります。 これによって、有効日が指定されたアイテムの追加と削除のメカニズムが提供されますが、プロパティに過去の有効日が指定されたアイテムも含まれている場合、過去の有効日が指定されたアイテムは変更できないのでエラーが返されます。 現在の有効日が指定されたアイテムも含まれている場合、そのアイテムは無視されます。 これにより、クライアントが呼び出すため`Get()`で、`getHistoryItems`パラメーターを False に設定し、将来の発効項目を変更または新しい将来の発効、項目を追加し、構造内のパラメーターとして渡す、`UpdateEx()`関数。  
  
 コンポーネント インターフェイスにキーがない場合、たとえば、インスタンスが 1 つしか存在できないような場合、`UpdateEx()` メソッドは次のような形式になります。  
  
```  
UpdateEx(correctionMode, interactiveMode, properties)  
```  
  
> [!NOTE]
>  BizTalk Adapter for PeopleSoft Enterprise の `UpdateEx()` メソッドが提供されるのは、コンポーネント インターフェイスで PeopleSoft の `Get` および `Save` 関数が有効になっている場合です。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)