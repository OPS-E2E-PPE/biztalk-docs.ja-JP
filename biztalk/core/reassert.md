---
title: 再アサート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22fcc8be7760d85a12cb05c53137177703c0fa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269650"
---
# <a name="reassert"></a>再アサート
*Reassert*を呼び出す意味、 **Assert**エンジンに既にあるオブジェクトに対して関数の作業メモリです。 reassert コマンドは、オブジェクトに対して retract コマンドを発行し、続けて assert コマンドを発行することと同じです。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 最初にオブジェクトが取り消され、述語またはアクション内でオブジェクトを使用しているルールの議題に関するアクションが削除されます。 オブジェクトは作業メモリにアサートされ、新たにアサートされたオブジェクトとして評価されます。 したがって、述語内でオブジェクトを使用するルールが再評価され、そのアクションが議題に適切に追加されます。 以前に評価される規則**true**とのみを使用して、アクション内のオブジェクトが議題に再び追加します。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 ときに最上位レベル**TypedXmlDocument** (**TXD**) 再アサートは、子**TXD**s 時に作成される最上位レベル**TXD**の初期値アサートされる子の状態に応じて異なる動作がある**TXD**s。 場合は、新しい子ノードまたは子ノードがダーティの場合、つまり、そのフィールドの少なくとも 1 つが変更されているポリシーで、ルールのアクション、アサートを使用して、またはアクションを再アサートは子ノードで実行されます。 ダーティではない既存の子ノードは、作業メモリに残されます。 次の例は、親ノードが再アサートされたときの子ノードの動作を説明する簡単なシナリオです。  
  
 3 つを使用する必要があると**TXD**作業メモリに現在 s: **P**、 **C**1、 **C**2、および**C**3 です。 **P**最上位レベル**TXD**、親ノードです。 各子ノードには、フィールドが含まれています。 **x**です。  
  
 **P**  
  
 **C**1 (**C**1 **。x** = 1)  
  
 **C**2 (**C**2 **。x** = 1)  
  
 **C**3 (**C**3 **。x** = 1)  
  
 次に、ルール アクションの結果として、次の操作が実行されたと仮定します。  
  
-   フィールド (**x**) の場合は値**C**2 を更新します。  
  
-   **C**3 がユーザー コードを使用して削除します。  
  
-   追加の子ノードでは、 **D**に追加**P**ユーザー コードを使用しています。  
  
> [!NOTE]
>  エンジンが関知しない操作によってビジネス ルール エンジンがノードをダーティであると識別することはありません。 たとえば、外部アプリケーション内でプログラムによってノードが追加、削除、または変更された場合です。  
  
 作業メモリ内のオブジェクトの新しい表現は次のようになります。  
  
 **P**  
  
 **C**1 (**C**1 **。x** = 1)  
  
 **C**2 (**C**2 **。x** = *0*)  
  
 **D**  
  
 ここで、再アサート**P**です。次に子ノードの動作を簡単に説明します。  
  
-   ノード**C**そのフィールドが更新された後にダーティになったために、2 が再アサートします。  
  
-   ノード**C**3 は作業メモリから取り消されます。  
  
-   ノード**D**が作業メモリにアサートします。  
  
-   ノード**C**する前に更新されませんでしたので 1 の作業メモリに変更されないまま**P**が再アサートします。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 場合**Reassert**で発行される、 **TypedDataRow**、その行が取り消され、作業メモリにアサートされます。 場合**Reassert**で発行される、 **TypedDataTable**、関連付けられているすべて**TypedDataRow**s が取り消され、アサートされます。  
  
## <a name="dataconnection"></a>DataConnection  
 すべて**TypedDataRow**使用して取得された、 **DataConnection**が取り消されます。 使用するすべての述語、 **DataConnection**はし、再評価され、 **DataConnection**に関連するを作成するクエリで**TypedDataRow**s。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)