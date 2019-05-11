---
title: 再アサート |Microsoft Docs
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
ms.openlocfilehash: 23cebbb268e57d71a1702a03d2516892c1851e8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398247"
---
# <a name="reassert"></a>再アサート
*再アサート*を呼び出す意味、 **Assert**エンジンにあるオブジェクトに対して関数の作業メモリ。 Reassert コマンドは、続けて assert コマンドは、オブジェクトに対して retract コマンドの発行と同じです。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 オブジェクトが最初に取り消され、(述語またはアクションの場合) 内のオブジェクトを使用するルールの議題に関するアクションが削除されます。 オブジェクトが作業メモリにアサートしが新しくアサートされている任意のオブジェクトとして評価します。 つまり、述語内でオブジェクトを使用するルールが再評価され、そのアクションが議題に適切に追加されます。 以前に評価されるルール**true**とのみを使用して、アクション内のオブジェクトがある、議題に再び追加します。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 ときに最上位レベル**TypedXmlDocument** (**TXD**) 再アサートされて、子**TXD**があるときに作成されます最上位レベル**TXD**最初にはアサートされる子の状態に応じて異なる動作がある**TXD**秒。 場合は、新しい子ノードまたはがダーティの場合、そのフィールドの少なくとも 1 つが変更されているポリシーで、ルールのアクション、アサートを使用して、つまりまたはアクションを再アサートする子ノードが子ノードで実行されます。 ダーティでない既存の子ノードは、作業メモリに残ります。 次の例は、その親ノードが再アサートされたときに、子ノードの動作を説明する簡単なシナリオです。  
  
 3 つを使用する必要があると仮定**TXD**作業メモリに現在の秒。**P**、 **C**1、 **C**2、および**C**3。 **P**最上位レベル**TXD**、親ノードです。 各子ノードには、フィールドが含まれています。 **x**します。  
  
 **P**  
  
 **C**1 (**C**1 **。x** = 1)  
  
 **C**2 (**C**2 **。x** = 1)  
  
 **C**3 (**C**3 **。x** = 1)  
  
 次に、ルール アクションの結果として、次の操作が実行されたと仮定します。  
  
-   フィールド (**x**) の場合は値**C**2 が更新されます。  
  
-   **C**ユーザー コードを使用して 3 が削除されます。  
  
-   追加の子ノード、 **D**に追加されます**P**ユーザー コードを使用しています。  
  
> [!NOTE]
>  ノードはないダーティであるが、エンジンが関知しない操作からビジネス ルール エンジン。 などの追加、削除、または外部アプリケーションでプログラムでノードを変更します。  
  
 作業メモリ内のオブジェクトの新しい表現は次のとおりです。  
  
 **P**  
  
 **C**1 (**C**1 **。x** = 1)  
  
 **C**2 (**C**2 **。x** = *0*)  
  
 **D**  
  
 ここで、再アサート**P**します。子ノードの動作を以下にまとめました。  
  
-   ノード**C**更新されているそのフィールドの後にダーティになったため、2 がアサートします。  
  
-   ノード**C**3 が作業メモリから取り消されます。  
  
-   ノード**D**作業メモリにアサートされます。  
  
-   ノード**C**する前に更新されていないために、1 は未変更のままで、作業メモリ**P**が再アサートされます。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 場合**再アサート**で発生したは、 **TypedDataRow**、その行が取り消され、作業メモリにアサートされます。 場合**再アサート**で発生したは、 **TypedDataTable**、関連するすべて**TypedDataRow**s が取り消され、アサートされます。  
  
## <a name="dataconnection"></a>DataConnection  
 すべて**TypedDataRow**して取得された、 **DataConnection**が取り消されます。 使用するすべての述語、 **DataConnection**は再評価、原因、 **DataConnection**を作成、関連するクエリを再実行する**TypedDataRow**s。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)