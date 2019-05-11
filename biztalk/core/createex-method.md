---
title: CreateEx メソッド |Microsoft Docs
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
ms.openlocfilehash: 23163739b18febd5642a704a6910241928e85730
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390117"
---
# <a name="createex-method"></a>CreateEx メソッド
一意なキーと指定されたプロパティのセットを使用して新しいレコードを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Key in/out parameter`|個々 のキー パラメーター (key1、key2、...keyn) を指定する必要があります。<br /><br /> このキーのセットがサーバー データベースに存在する必要があります、これは、一意でなければなりません。<br /><br /> これらのキーは、特定のコンポーネント インターフェイスに定義された CreateEx Keys のセットに対応します。|  
|`interactiveMode`|エラー処理します。<br /><br /> Microsoft BizTalk Adapter for PeopleSoft Enterprise が PeopleSoft が提供する Api、;、コンポーネント インターフェイスで個々 のフィールドを読み書きするを使用してコンポーネント インターフェイスでプロパティにアクセスするときただし、これらの変更は、一度に 1 つずつ PeopleSoft サーバーに反映されませんが。 代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と連携する) では、すべての変更をパッケージ化し、1 つのパッケージ内のサーバーに変更を送信します。<br /><br /> 個々 の更新プログラムのいずれかが失敗した場合、汎用的なエラーが返されますが、実際のエラーを特定していません。 対話モードを TRUE に設定、すべてのフィールドの更新プログラムは、サーバーに個別に送信されます。 これは、パフォーマンスに大きな影響がありますが (たとえば、フィールドを設定するために無効な値が使用されます) 場合、更新が失敗した場合は、特定のエラー情報は提供します。<br /><br /> InteractiveMode は最大のパフォーマンスを提供し、フィールド更新レベルでエラーを報告を提供します。 この機能を正しく使用するには、interactiveMode を FALSE に設定すると、通常の呼び出しが行われることをお勧めします。 あるは影響はないパフォーマンスにします。 エラーが返された場合、interactiveMode フラグを TRUE に設定と同じ呼び出しを再試行できます。 呼び出しが失敗したときに、サーバーより正確なエラー メッセージを返します。|  
|`properties`|コンポーネント インターフェイスのすべてのプロパティを含む構造体。 ときに、`CreateEx`メソッドが呼び出されると、これらのプロパティは、指定されたキーで作成されたレコードに挿入されます。|  
  
## <a name="remarks"></a>コメント  
 場合によってを呼び出す一般的`CreateEx()`せず、明示的なキーのセットが、`CreateEx`関数は、キーを返します。 この動作は、実行されるサーバーで PeopleCode でサポートされます。 たとえば、注文書を作成するクライアント可能性があります、次に利用できる PO 番号がわからない。 [次へ] を指定すると、PO 番号キーとして、呼び出し peoplecode、次に利用できる PO 番号を決定します。 この情報は、入力/出力のキー パラメーターを使用して、呼び出し元のクライアントに返す必要があります。  
  
> [!NOTE]
>  このメカニズムが機能するには、キーはレベル 0 のプロパティをあるも必要があります。 それ以外の場合、元のキーが返されます。  
  
 BizTalk Adapter for PeopleSoft Enterprise`CreateEx()`コンポーネント インターフェイスで PeopleSoft の作成と保存の機能が有効になっている場合、メソッドが用意されています。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)