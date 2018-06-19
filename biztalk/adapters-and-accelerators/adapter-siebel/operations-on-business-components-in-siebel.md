---
title: Siebel ビジネス コンポーネントに対する操作 |Microsoft ドキュメント
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
ms.openlocfilehash: fc634d48d4a39e610247edbab98104bc3c6da379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223618"
---
# <a name="operations-on-business-components-in-siebel"></a>Siebel ビジネス コンポーネントに対する操作
Siebel ビジネス コンポーネントは、1 つの構造に 1 つまたは複数のデータベース テーブルから列を関連付ける論理エンティティです。 アダプターのクライアントは、アダプターを使用して、Siebel ビジネス コンポーネントでは、次の操作を実行できます。  
  
-   **挿入**です。 アダプターのクライアントは、ビジネス コンポーネントに 1 つまたは複数のレコードを挿入できます。  
  
-   **クエリ**です。 アダプターのクライアントは、ビジネス コンポーネントの 1 つまたは複数のレコードを照会できます。 この操作は、次のパラメーターを入力として取得します。  
  
    -   SearchExpr:、検索式が含まれています。 この検索式に対して指定されたビジネス コンポーネントの下のすべてのレコードが比較され、一致するレコードは、アダプターのクライアントに返されます。  
  
    -   SortSpec: 検索式に一致する複数のレコードがある場合は、この仕様はレコードが返される順序を決定します。 このパラメーターはオプションです。  
  
    -   QueryFields: では、返されたレコードのフィールドのサブセットのみの値を取得するアダプターのクライアントを使用できます。 このパラメーターはオプションです。  
  
        > [!NOTE]
        >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] QueryField パラメーターでは、ビジネス コンポーネントのクエリ操作で元の名前の使用をサポートしています  
  
-   **更新**です。 アダプターのクライアントは、ビジネス コンポーネントで 1 つまたは複数のレコードを更新できます。  
  
-   **削除**です。 アダプターのクライアントは、Id のセットを指定または検索式を提供することにより、ビジネス コンポーネントで 1 つまたは複数のレコードを削除できます。  
  
    > [!NOTE]
    >  その他のパラメーターに加えて、クエリ、更新、および削除操作は、ViewMode パラメーターを受け取る。 このパラメーターは、ユーザーのアクセス許可を決定する整数を取得します。 ViewMode パラメーターとこれらの操作に関するその他のパラメーターの詳細については、下にあるビジネス コンポーネント操作の要求メッセージを参照してください。[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)です。  
  
 詳細については。  
  
-   BizTalk Server を使用してビジネス コンポーネントの操作を実行するを参照してください[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)です。  
  
-   WCF サービス モデルを使用してビジネス コンポーネントの操作を実行するを参照してください[、Siebel アダプターの WCF サービス モデルを使用してビジネス コンポーネントでの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)です。  
  
-   WCF チャネル モデルを使用してビジネス コンポーネントの操作を実行するを参照してください[、Siebel アダプターの WCF サービス モデルを使用してビジネス コンポーネントでの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)です。  
  
-   メッセージの構造体と SOAP アクションを使用してビジネス コンポーネントの操作を実行するを参照してください[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)です。  
  
## <a name="operations-on-business-components-with-mvg-fields"></a>MVG フィールドのビジネス コンポーネントに対する操作  
 Siebel ビジネス コンポーネントは、結合または複数値を持つグループ (MVG) を使用して他のビジネス コンポーネントからフィールドを取得することもできます。 ビジネス コンポーネントはすべての表示された挿入、クエリ、Update、および削除操作、に加えてアダプター クライアントは、アダプターを使用して、Siebel ビジネス コンポーネントでは、次の操作を実行できます。  
  
-   **関連付ける**です。 アダプターのクライアントには、親の検索式を指定することによってレコードと子レコードを関連付けることができます。 これは、MVG フィールドのビジネス コンポーネントに対してのみ適用されます。 検索式では、親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルター処理する必要があります。  
  
-   **関連付けを解除**です。 アダプターのクライアントには、親の検索式を指定することによってレコードと子レコードを切り離すこともできます。 これは、MVG フィールドのビジネス コンポーネントに対してのみ適用されます。 検索式では、親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルター処理する必要があります。  
  
-   **Query_ [MVG_Child_Business_Comp]** です。 アダプターのクライアントは、親レコードと MVG フィールド名を指定して、親レコードに関連付けられている子レコードを照会できます。 これは、MVG フィールドのビジネス コンポーネントに対してのみ適用されます。  
  
    > [!NOTE]
    >  その他のパラメーターに加えて、これらの操作は、ViewMode パラメーターを受け取る。 このパラメーターは、ユーザーのアクセス許可を決定する整数を取得します。 ViewMode パラメーターとこれらの操作に関するその他のパラメーターの詳細については、下にあるビジネス コンポーネント操作の要求メッセージを参照してください。[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)です。  
  
 詳細については。  
  
-   使用してビジネス コンポーネントでこれらの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[MVG フィールドを使用して BizTalk Server と Siebel アダプターとビジネス コンポーネントでの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)です。  
  
-   WCF サービスのモデルを使用してビジネス コンポーネントでこれらの操作を実行するを参照してください[WCF サービス モデルを使用して、Siebel アダプターと MVG フィールドのビジネス コンポーネントでの操作を実行](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)です。  
  
-   メッセージの構造体とこれらの操作用の SOAP アクションを参照してください[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)です。  
  
## <a name="operations-on-business-components-with-picklist-fields"></a>候補リストのフィールドのビジネス コンポーネントに対する操作  
 ビジネス コンポーネントの候補リストのフィールドの種類は、ユーザーが特定の Siebel システムに渡す値を選択できる値のコレクションを構成します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]候補リストのフィールドのビジネス コンポーネント操作をサポートします。 候補リストのフィールドを含むビジネス コンポーネントでは、操作では、前の段落で説明されているとその他のビジネス コンポーネント操作と同じです。 ただし、候補リストの種類、に応じて異なる場合があります、ビジネス コンポーネントへの入力値は。 候補リストとその種類の詳細については、Siebel のドキュメントを参照してください。  
  
 列挙型の候補リストとして、アダプターで表示されたいずれかの候補リスト型、静的な境界のある候補リストは、デザイン時にアダプターによって生成されたメタデータ内の型。 これには、実行時に候補リストの種類を指定する必要があります値の静的セットが含まれています。  静的範囲指定された候補リストの値を指定する、中には、常に、セットに属している値を指定する必要があります。  
  
 候補リストのフィールドのビジネス コンポーネントの操作を実行するメッセージの構造は、前述の他のビジネス コンポーネント操作のメッセージ構造に似ています[ビジネスコンポーネント操作のメッセージスキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 詳細については。  
  
-   メッセージの構造の候補リストのフィールドを含むビジネス コンポーネントを参照してください[候補リスト操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schema-for-picklist-operations.md)です。  
  
-   候補リストのフィールドが含まれるビジネス コンポーネント操作を実行するを参照してください[候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントでの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)