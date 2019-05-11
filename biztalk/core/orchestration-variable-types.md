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
ms.openlocfilehash: 7ff157896d15b99685379bef16c0b3fc87e2e76e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322502"
---
# <a name="orchestration-variable-types"></a>オーケストレーション変数の型
次の定義済みの型の変数を宣言することができます。  

|||||  
|-|-|-|-|  
|boolean|byte|char|DATETIME|  
|Decimal|double|int16|Int32|  
|int64|long|sbyte|1 つ|  
|string|timespan|uint16|uint32|  
|uint64||||  

 いずれかの変数を宣言することもできます。プロジェクトで参照されている NET ベースの型。  

## <a name="considerations-for-declare-orchestration-variables"></a>オーケストレーション変数を宣言に関する考慮事項  
 オーケストレーションを宣言する場合、変数は、次を検討してください。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 特定のコンテンツ ベースのルーティングのシナリオがサポートする複数値のコンテキスト プロパティは、オーケストレーションでこのようなプロパティを使用することはできません。  

- 中断とオーケストレーションの変数である必要がありますすべてのオーケストレーションの退避をサポートするために持つことができる状態の永続化されます。  通常、これは、変数の型またはクラスがシリアル化またはストリーミングによって実現されます。  

- これらは。NET ベースの型 (クラス) は、シリアル化可能なクラスである必要があります。  "[Serializable]"属性で宣言されているか、ISerializable .NET インターフェイス (System.Runtime.Serialization 名前空間の) 内に明示的に実装しているか、実装できます。  

- 場合、します。NET ベースの型は、基になる COM コンポーネントの実際には、ランタイム呼び出し可能ラッパー (RCW)、その COM コンポーネントでは RCW がシリアル化可能な .NET クラス (IPersistStream、ipersiststreaminit など) に必要なインターフェイスを実装する必要があります。  

- 任意です。NET ベース (または、基になる COM) 型は、オーケストレーションのフローで実行して、これらの型のメソッドは、(競合リソースなど) を使用するなどのオーケストレーションの実行を遅延しない必要があります。  これらの型の実装によってリソースの競合が呼び出し元のオーケストレーションを実行するホスト インスタンスに反映されます。
