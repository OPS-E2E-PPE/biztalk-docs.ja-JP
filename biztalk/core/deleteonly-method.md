---
title: DeleteOnly メソッド |Microsoft Docs
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
ms.openlocfilehash: bf006e4ba2db1378a207c4e20136310b6977c928
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352274"
---
# <a name="deleteonly-method"></a>DeleteOnly メソッド
コレクション内の項目を削除することができます。  
  
## <a name="syntax"></a>構文  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`key`|一連のパラメーターを指定する必要があります。 この一連のキーは、サーバー データベースに存在する必要があります。 またはエラーが発生します。 これらのキーは、特定のコンポーネント インターフェイスに対して定義されている一連の Get キーに対応します。|  
|`correctionMode`|ブール型のフラグ。 True の場合、コレクションの過去の発効アイテムの削除を可能に設定するとします。 具体的には、EFFDT が現在有効な日付より前にある項目の削除ができます。 なしこのフラグを TRUE に設定すると、これらの項目を変更しても結果 PeopleSoft サーバーから返されるエラー。 **注:**`correctionMode`引数は、effective-dated 項目を含むコンポーネント インターフェイスに対してのみ公開されます。 それ以外の場合、引数の一部としては表示されません。|  
|`interactiveMode`|エラー処理に使用されます。<br /><br /> BizTalk Adapter for PeopleSoft Enterprise が PeopleSoft が提供する Api、;、コンポーネント インターフェイスで個々 のフィールドを読み書きするを使用してコンポーネント インターフェイスでプロパティにアクセスするときただし、これらの変更は、一度に 1 つずつ PeopleSoft サーバーに反映されませんが。 代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と連携する) では、すべての変更をパッケージ化し、1 つのパッケージ内のサーバーに変更を送信します。 個々 の更新プログラムのいずれかが失敗した場合、汎用的なエラーが返されますが、実際のエラーを特定していません。 対話モードを TRUE に設定、すべてのフィールドの更新プログラムは、サーバーに個別に送信されます。 これは、パフォーマンスに大きな影響がありますが (たとえば、フィールドを設定するために無効な値が使用されます) 場合、更新が失敗した場合は、特定のエラー情報は提供します。<br /><br /> `interactiveMode`パラメーターは、最大のパフォーマンスを提供し、フィールド更新レベルでエラーを報告を提供します。 この機能を正しく使用するをお勧めして通常の呼び出しを行った`interactiveMode`を FALSE に設定します。 あるは影響はないパフォーマンスにします。 エラーが返された場合、interactiveMode フラグを TRUE に設定と同じ呼び出しを再試行できます。 呼び出しが失敗したときに、サーバーより正確なエラー メッセージを返します。|  
|`properties`|サーバーに存在する構造のサブセットが含まれています。 リーフであるすべての項目が削除されます。|  
  
## <a name="remarks"></a>コメント  
 プロパティは、同じデータとして型を持つ、`CreateEx`または`UpdateEx`はコンポーネント インターフェイスのメソッドただし、キー値のみが重要です。 キー以外の値は無視されます。 キーの値で、サーバー上のものと一致する必要があります、それ以外の場合、例外が発生します。  
  
 キーの値の使用を次に示します。 場合は、コレクションには、項目が含まれています。  
  
- item0  
  
- item1  
  
- item2  
  
- item3  
  
  Item1 と item3 を削除するには、プロパティの item1 と item3 のキーを指定します。  
  
- item1  
  
- item3  
  
  呼び出しの後は、サーバーは、残りの項目をコレクション内に。  
  
- item0  
  
- item2  
  
  2 番目の例では、他のコレクションを格納している項目を示します。  
  
- item0  
  
  -   item0a  
  
- item1  
  
  -   item1a  
  
  -   item1b  
  
  -   item1c  
  
- item2  
  
  -   item2a  
  
  -   item2b  
  
  Item1b と item2 のすべてを削除するには、item1b と item2 へのキーを提供します。  
  
- item1  
  
  -   item1b  
  
- item2  
  
  Item2 の空のサブ コレクションを用意すると、リーフに有効にしてそのサブブランチ全体が削除されます。 呼び出しの後、サーバーは、残りの項目があります。  
  
- item0  
  
  -   item0a  
  
- item1  
  
  -   item1a  
  
  -   item1c  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)