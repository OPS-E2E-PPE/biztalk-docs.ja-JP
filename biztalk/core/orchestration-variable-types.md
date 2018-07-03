---
title: オーケストレーション変数の型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 34990be2-35b6-40ec-b107-42a1c7b45aca
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d3128d8cb3298dbab7e2394d55f6c2d6ff6ac3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971739"
---
# <a name="orchestration-variable-types"></a>オーケストレーション変数の型
次の定義済み型の変数を宣言できます。  

|||||  
|-|-|-|-|  
|boolean|byte|char|DATETIME|  
|Decimal|double|int16|int32|  
|int64|long|sbyte|single|  
|string|timespan|uint16|uint32|  
|uint64||||  

 プロジェクト内で参照されている任意の .NET ベースの型の変数を宣言することもできます。  

## <a name="considerations-for-declare-orchestration-variables"></a>オーケストレーション変数を宣言する際の考慮事項  
 オーケストレーション変数を宣言するときは、次の点を考慮してください。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、特定のコンテキストベースのルーティング シナリオに対して複数値のコンテキスト プロパティをサポートしていますが、このようなプロパティをオーケストレーションで使用することはできません。  

- オーケストレーションの中断と退避をサポートするには、すべてのオーケストレーション変数がその状態を永続化できるようになっている必要があります。  通常、これは変数の型またはクラスをシリアル化またはストリーミング化可能にすることで実現します。  

- これらの .NET ベースの型 (クラス) はシリアル化可能なクラスである必要があります。  これは、"[Serializable]" 属性を使用して宣言するか、ISerializable .NET インターフェイス (System.Runtime.Serialization 名前空間内) を明示的に実装することによって実装できます。  

- .NET ベースの型が、実際には基になる COM コンポーネントのランタイム呼び出し可能ラッパー (RCW) である場合、その COM コンポーネントでは RCW がシリアル化可能な .NET クラス (IPersistStream、IPersistStreamInit など) となるために必要なインターフェイスを実装する必要があります。  

- .NET ベース (または基になる COM) の型はオーケストレーションのフロー内で実行されるので、これらの型のメソッドはオーケストレーションの実行を (リソースの競合などにより) 遅延しないようにする必要があります。  また、これらの型の実装によるリソースの競合は、呼び出し元のオーケストレーションを実行するホスト インスタンスに影響を及ぼします。
