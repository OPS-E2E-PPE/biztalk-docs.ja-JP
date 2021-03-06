---
title: 子の順序に関する注意事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ee4c9bf7fe2b6a43951032f5043489f73d94bde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357354"
---
# <a name="child-order-considerations"></a>子の順序に関する注意事項

## <a name="requirements-for-header-in-a-flat-file"></a>フラット ファイルのヘッダーにするための要件
設定するときに特別な考慮事項を適用する、区切られたフラット ファイルに関連する 2 つのシナリオがある、**子の順序**プロパティ。 このようなシナリオがフラット ファイル ドキュメントが、ヘッダー、本文、および必要に応じて、トレーラーである状況に関係する最初。 これらのシナリオで、次の要件を確認する必要があります。  

- 設定する必要があります、**子の順序**するヘッダーの (区切られた) ルート レコードのプロパティ**後置**します。  

- 設定する必要があります、トレーラーが存在する場合、**子の順序**プロパティ本体の (区切られた) ルート レコード**後置**します。  

- 設定することがあります、トレーラーが存在しない場合、**子の順序**プロパティ本体の (区切られた) ルート レコード**プレフィックス**、 **"挿入辞"**、または**後置**.  

- トレーラーが存在する場合は、設定、**子の順序**プロパティには、そのトレーラーの (区切られた) ルート レコード**プレフィックス**、 **"挿入辞"**、または**後置**.  

- 設定することがあります、**子の順序**ヘッダー、本文、およびトレーラーの区切られた下位レコード プロパティ**プレフィックス**、 **"挿入辞"**、または**後置**.  

  区切られたフラット ファイルの 2 番目のシナリオに関連して、**子の順序**プロパティは、ノードのランタイム コンポーネントの想定に従ってこのプロパティを設定する必要があります。 正しい設定、**子の順序**プロパティが明らかでないルートとグループ ノードの場合、次のシナリオに示すようにします。  

- **ルート ノードです。** 一般的なフラット ファイル構造を持つは、レコードと CR/LF の組み合わせで構成されていますを検討してください。 区切り記号は、ファイル内のレコードを分離し、レコード、区切り記号、レコード、区切り記号、および具合に、シーケンスが通常はします。 このような状況で、区切り記号常に依存してに対応するデータを**子の順序**プロパティの設定の**後置**します。  

- **グループ ノード:** スキーマの BizTalk Server および XSD 表記に示すように、グループ ノードのインスタンス メッセージのフラット ファイル表記で明示的に存在していません。 行アイテムごとに、レコードのコレクションを格納する注文書 (PO) を考慮し、それらのレコードの繰り返しを 1 つの PO に複数の行項目を表す何度もします。 このようなメッセージのスキーマには、繰り返しの一連の (場合によっては概念) のコンテナーとして機能する LineItems というノードが含まれます可能性があります: フラット ファイル表記のインスタンス メッセージには、LineItems コンテナーはによって表される、本質的に概念データと区切り記号の適切な順序インスタンス メッセージの XML 表現、LineItems コンテナーの形式で明示的に存在する、 **LineItems** XML 内の要素。  

  ルート ノードと 1 つだけのグループ ノードを含むメッセージを検討してください。 ルート ノードへの入力ストリームの最後の区切り記号が属する場所を簡単になります。 そのため、概念のループでデータ/区切り記号シーケンスでは、1 つまたは複数の品目レコードがだけです。 場合にのみ 1 つ以上の品目レコードがこれらを分離する区切り記号はあるがある場合。 ある場合は、区切り記号の数が 1 つ未満れるのセットと区切り記号が挿入辞と呼ばれる構造で区切られた項目の間に配置します。  

## <a name="see-also"></a>参照  
- [区切り記号付きレコードに関する注意](../core/delimited-record-considerations.md)   
- **子の順序 (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
