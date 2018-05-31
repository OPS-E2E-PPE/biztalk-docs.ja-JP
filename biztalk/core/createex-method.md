---
title: CreateEx メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateEx method
ms.assetid: b62bbe25-b24d-42a7-a44c-c83521a6f0a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b163bfbe7811c37208297aa0a61bfe91cabacde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238290"
---
# <a name="createex-method"></a>CreateEx メソッド
一意なキーと指定されたプロパティを使用して新しいレコードを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`Key in/out parameter`|個々のキー パラメーター (key1、key2、... keyn)。このパラメーターは必須です。<br /><br /> このキー セットは、サーバー データベースに存在しないものである、つまり、一意である必要があります。<br /><br /> これらのキーは、特定のコンポーネント インターフェイスで定義された CreateEx Keys のセットに対応します。|  
|`interactiveMode`|エラー処理。<br /><br /> コンポーネント インターフェイスでプロパティにアクセスする場合、Microsoft BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft から提供されている API を使用してコンポーネント インターフェイス内の個々のフィールドを読み書きします。ただし、これらの変更は一度に 1 つずつ PeopleSoft サーバーに伝達されるわけではありません。 代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と対話) が、すべての変更を 1 つのパッケージにしてサーバーに送信します。<br /><br /> 個別の更新が失敗した場合、汎用エラーが返されます。このエラーは、実際のエラーを特定しません。 対話モードを TRUE に設定することで、すべてのフィールド更新がサーバーに個別に送信されます。 これによってパフォーマンスに大きな影響が及びますが、更新が失敗した場合 (たとえば、フィールドの設定に無効な値が使用された場合) には、具体的なエラー情報が提供されます。<br /><br /> interactiveMode は最大のパフォーマンスを発揮し、フィールド更新レベルでエラーを報告します。 この機能を正しく使用できるように、interactiveMode を FALSE に設定して通常の呼び出しを行うことをお勧めします。 パフォーマンスへの影響はありません。 エラーが返された場合は、interactiveMode フラグを TRUE に設定して同じ呼び出しを再試行できます。 呼び出しが失敗した場合、サーバーはより正確なエラー メッセージを返します。|  
|`properties`|コンポーネント インターフェイスのすべてのプロパティを含む構造体。 `CreateEx` メソッドが呼び出されると、これらのプロパティは、指定されたキーで作成されたレコードに挿入されます。|  
  
## <a name="remarks"></a>解説  
 明示的なキー セットを指定せずに `CreateEx()` を呼び出すのが一般的な場合もありますが、`CreateEx` 関数はキーを返します。 この動作は、サーバーで実行される PeopleCode でサポートされています。 たとえば、注文書を作成する場合、クライアントには次に利用できる PO 番号がわからないことがあります。 PO 番号キーに NEXT を指定して呼び出すことで PeopleCode が実行され、次に利用できる PO 番号が設定されます。 この情報は、in/out キー パラメーターを使用して呼び出し元のクライアントに返される必要があります。  
  
> [!NOTE]
>  このしくみが機能するには、キーはレベル 0 のプロパティもする必要があります。 それ以外の場合、元のキーが返されます。  
  
 BizTalk Adapter for PeopleSoft Enterprise の `CreateEx()` メソッドが提供されるのは、コンポーネント インターフェイスで PeopleSoft の Create 関数および Save 関数が有効になっている場合です。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)