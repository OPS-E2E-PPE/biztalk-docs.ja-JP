---
title: UpdateEx メソッド |Microsoft Docs
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
ms.openlocfilehash: 5ac317a9c91f13dce2dadf74b3027ebf4d33390f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398641"
---
# <a name="updateex-method"></a>UpdateEx メソッド
入力キー パラメーター (key1、key2、... に基づいてプロパティを更新するために使用 keyn)。 使用する場合`UpdateEx`コレクション内の項目を削除することはできません。 別のメソッドには、削除が容易になります。 詳細については、次を参照してください。 [DeleteOnly メソッド](../core/deleteonly-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
UpdateEx (key1, key2, ... keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`key`|サーバーのデータベース、またはエラーに存在する必要がありますパラメーターのセットが発生します。 これらのキーは、特定のコンポーネント インターフェイスに対して定義されている一連の Get キーに対応します。|  
|`correctionMode`|ブール型のフラグ。 True の場合をフィールドの値を更新するか、新しい項目をコレクションに挿入することで、effective-dated 項目とのコンポーネント インターフェイスの変更を可能に設定するとします。 具体的には、EFFDT が現在有効な日付より前にある項目を変更することができます。 なしこのフラグを TRUE に設定すると、これらの項目を変更しても結果 PeopleSoft サーバーから返されるエラー。<br /><br /> `correctionMode`引数は、effective-dated 項目を含むコンポーネント インターフェイスに対してのみ公開されます。 それ以外の場合、引数の一部としては表示されません。<br /><br /> 設定はしないで`correctionMode`を運用環境で TRUE にします。 (これも、推奨事項は PeopleSoft から。)過去の EFFDT キーによって既に発生しているイベントを変更する必要があります。 これは、ため、監査証跡を作成できます。 `correctionMode`フラグ`UpdateEx`この安全性のメカニズムは行われませんでした。 推奨される方法は過去のイベントの項目、フィールドを設定し、(削除) ではなく追加で非アクティブになる更新された項目。|  
|`interactiveMode`|エラー処理に使用されるフラグ。<br /><br /> BizTalk Adapter for PeopleSoft Enterprise ではコンポーネント インターフェイスで個々 のフィールドを読み書きする PeopleSoft が提供する Api を使用してコンポーネント インターフェイスでプロパティにアクセスするときただし、これらの変更は、一度に 1 つずつ PeopleSoft サーバーに反映されませんが。 代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と連携する) では、すべての変更をパッケージ化し、1 つのパッケージ内のサーバーに変更を送信します。 個々 の更新プログラムのいずれかが失敗した場合、汎用的なエラーが返されますが、実際のエラーを特定していません。 対話モードを TRUE に設定、すべてのフィールドの更新プログラムは、サーバーに個別に送信されます。 これは、パフォーマンスに大きな影響がありますが (たとえば、フィールドを設定するために無効な値が使用されます) 場合、更新が失敗した場合は、特定のエラー情報は提供します。<br /><br /> `interactiveMode`最大のパフォーマンスを提供し、エラー、フィールド更新レベルでレポートを提供します。 この機能を正しく使用するをお勧めして通常の呼び出しを行った`interactiveMode`を FALSE に設定します。 あるは影響はないパフォーマンスにします。 同じ呼び出しを再試行することができます、エラーが返された場合、`interactiveMode`フラグを TRUE に設定します。 呼び出しが失敗したときに、サーバーより正確なエラー メッセージを返します。|  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出すときにそのキーに対応するレコードのプロパティと、入力パラメーターのプロパティが置き換えられます。 元のレコードを含むすべてのコレクションが削除され、入力パラメーターで置き換えられます。 これらのコレクションのサイズはありません一致内でプロシージャ`UpdateEx`は既存のすべてのコレクション アイテムを削除し、指定したものを挿入します。  
  
 コンポーネント インターフェイスのプロパティに有効日が指定された項目が含まれている場合、プロパティのパラメーターは、元のリストが置き換えられるために未来の有効日が指定された項目を含める必要があります。 これを追加すると、将来の発効項目を削除する、メカニズムが提供します。ただし、過去の発効項目プロパティを含めることも、エラーが返されますので、過去の発効項目を変更することはできません。 現在の発効項目も含まれています、無視されます。 これによって、クライアントを呼び出す`Get()`で、`getHistoryItems`パラメーターを False に設定し、将来の発効項目を変更または新しい将来の発効の項目を追加および構造体をパラメーターとして渡す、`UpdateEx()`関数。  
  
 コンポーネント インターフェイスが 1 つだけのインスタンスが存在できるケースのように、キーを持たない場合、`UpdateEx()`メソッドの形式。  
  
```  
UpdateEx(correctionMode, interactiveMode, properties)  
```  
  
> [!NOTE]
>  BizTalk Adapter for PeopleSoft Enterprise`UpdateEx()`メソッドが提供される場合、PeopleSoft`Get`と`Save`コンポーネント インターフェイスでの機能が有効にします。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)