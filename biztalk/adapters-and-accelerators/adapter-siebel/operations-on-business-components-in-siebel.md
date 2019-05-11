---
title: Siebel ビジネス コンポーネントに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business components, operations on
- operations, on business components
- operations, on business components with picklist fields
ms.assetid: 5430a8bd-88eb-4851-92e3-676ca83780c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b023076c797de87c84e6efb91afa160c8a565665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371231"
---
# <a name="operations-on-business-components-in-siebel"></a>Siebel ビジネス コンポーネントに対する操作
Siebel ビジネス コンポーネントは、1 つまたは複数のデータベース テーブルから列を 1 つの構造に関連付ける論理エンティティです。 アダプターのクライアントは、アダプターを使用して、Siebel ビジネス コンポーネントでは、次の操作を実行できます。  
  
- **挿入**します。 アダプター クライアントは、ビジネス コンポーネントに 1 つまたは複数のレコードを挿入できます。  
  
- **クエリ**します。 アダプター クライアントは、ビジネス コンポーネントの 1 つまたは複数のレコードを照会できます。 この操作は入力として、次のパラメーターを受け取ります。  
  
  - SearchExpr:検索式が含まれています。 指定されたビジネス コンポーネントの下のすべてのレコードが、この検索式と比較して、アダプターのクライアントに一致するレコードが返されます。  
  
  - SortSpec:検索式に一致する複数のレコードがある場合は、この仕様は、レコードが返される順序を決定します。 このパラメーターはオプションです。  
  
  - QueryFields:返されるレコードのフィールドのサブセットのみの値を取得するアダプターのクライアントを有効にします。 このパラメーターはオプションです。  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] QueryField パラメーターでは、ビジネス コンポーネントのクエリ操作で元の名前は使用をサポートしています  
  
- **Update**します。 アダプター クライアントは、ビジネス コンポーネントの 1 つまたは複数のレコードを更新できます。  
  
- **削除**します。 アダプター クライアントは、一連の Id を指定することで、または検索式を提供することで、ビジネス コンポーネントの 1 つまたは複数のレコードを削除できます。  
  
  > [!NOTE]
  >  その他のパラメーターだけでなく、クエリ、Update、Delete の各操作は、ViewMode パラメーターを受け取る。 このパラメーターは、ユーザーのアクセス許可を決定する整数値を取得します。 ViewMode パラメーターとこれらの操作に関するその他のパラメーターの詳細については、下のビジネス コンポーネント操作の要求メッセージを参照してください。[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)します。  
  
  詳細については。  
  
- BizTalk Server を使用してビジネス コンポーネントに対する操作を実行するを参照してください[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)します。  
  
- WCF サービス モデルを使用してビジネス コンポーネントに対する操作を実行するを参照してください[WCF サービス モデルを使用して Siebel アダプターでビジネス コンポーネントに対する操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)します。  
  
- WCF チャネル モデルを使用してビジネス コンポーネントに対する操作を実行するを参照してください[WCF サービス モデルを使用して Siebel アダプターでビジネス コンポーネントに対する操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)します。  
  
- メッセージの構造と SOAP アクションを使用してビジネス コンポーネントに対する操作を実行するを参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)します。  
  
## <a name="operations-on-business-components-with-mvg-fields"></a>MVG フィールドを持つビジネス コンポーネントに対する操作  
 Siebel ビジネス コンポーネントは、結合または複数の値のグループ (MVG) を使用して他のビジネス コンポーネントからフィールドを取得することもできます。 挿入、クエリ、更新、および削除の操作以外のすべてのビジネス コンポーネントに表示されるアダプターのクライアントは、アダプターを使用して、Siebel ビジネス コンポーネントでは、次の操作を実行できます。  
  
- **関連付ける**します。 アダプター クライアントには、親の検索式を指定してレコードと子レコードを関連付けることができます。 これは、MVG フィールドを持つビジネス コンポーネントにのみ適用できます。 検索式は、親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルター処理する必要があります。  
  
- **関連付けを解除**します。 アダプター クライアントには、親の検索式を指定してレコードと子レコードを切り離すこともできます。 これは、MVG フィールドを持つビジネス コンポーネントにのみ適用できます。 検索式は、親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルター処理する必要があります。  
  
- **[MVG_Child_Business_Comp] Query_** します。 アダプター クライアントは、親レコードと MVG フィールド名を指定することで、親レコードに関連付けられている子レコードを照会できます。 これは、MVG フィールドを持つビジネス コンポーネントにのみ適用できます。  
  
  > [!NOTE]
  >  その他のパラメーターだけでなく、これらの操作は、ViewMode パラメーターを受け取る。 このパラメーターは、ユーザーのアクセス許可を決定する整数値を取得します。 ViewMode パラメーターとこれらの操作に関するその他のパラメーターの詳細については、下のビジネス コンポーネント操作の要求メッセージを参照してください。[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)します。  
  
  詳細については。  
  
- 使用してビジネス コンポーネントでこれらの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[MVG フィールドを使用して BizTalk Server と Siebel アダプターを使用したビジネス コンポーネントに対する操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)します。  
  
- WCF サービス モデルを使用してビジネス コンポーネントでこれらの操作を実行するを参照してください[WCF サービス モデルを使用して Siebel アダプターで MVG フィールドを持つビジネス コンポーネントに対する操作を実行](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)します。  
  
- メッセージの構造体とこれらの操作用の SOAP アクションを参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)します。  
  
## <a name="operations-on-business-components-with-picklist-fields"></a>候補リストのフィールドでビジネス コンポーネントに対する操作  
 ビジネス コンポーネントの候補リスト フィールド型は、ユーザーが特定の Siebel システムに渡す値を選択できる値のコレクションを構成します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]候補リストのフィールドを持つビジネス コンポーネントに対する操作をサポートしています。 候補リストのフィールドを格納しているビジネス コンポーネントに対する操作は前の段落で説明されていると、他のビジネス コンポーネントに対する操作と同じです。 ただし、候補リストの種類によって異なる場合があります、ビジネス コンポーネントへの入力値は。 候補リストとその型の詳細については、Siebel のドキュメントを参照してください。  
  
 列挙型の候補リストとして、アダプターによって表示された候補リストの種類、静的の境界付けられた候補リストのいずれかでデザイン時にアダプターによって生成されたメタデータの種類。 これには、実行時に候補リストの種類を指定する必要があります値の静的なセットが含まれています。  静的範囲指定された候補リストの値を指定する、中には、常に、セットに属している値を指定する必要があります。  
  
 」の説明に従って、候補リストのフィールドでビジネス コンポーネントに対する操作を実行するメッセージの構造は、他のビジネス コンポーネントに対する操作のメッセージ構造に似ています[ビジネス コンポーネント操作のメッセージスキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 詳細については。  
  
-   メッセージの構造体が候補リストのフィールドを格納しているビジネス コンポーネントを参照してください[候補リスト操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schema-for-picklist-operations.md)します。  
  
-   候補リストのフィールドを含むビジネス コンポーネントに対する操作を実行するを参照してください[候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)