---
title: オーケストレーション変数を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: c387cd56-5443-4de2-bbda-be34b95cbe71
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876799a7baf58d7dacc8185d09d6f9d63a70127d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343253"
---
# <a name="how-to-add-orchestration-variables"></a>オーケストレーション変数を追加する方法
オーケストレーションの種類 ウィンドウでは、オーケストレーションのプロパティを管理することができます (とも呼ばれます**サービス**プロパティ)、パラメーター、ポート、メッセージ、およびその他の変数。 ポートとメッセージ、だけでなく、整数変数、ブール変数、文字列変数、または .NET クラスの変数を作成できます。  
  
 スコープに属する変数を管理するのにオーケストレーションの種類 ウィンドウを使用することもできます。  
  
### <a name="to-add-a-variable"></a>変数を追加するには  
  
1.  オーケストレーションの種類 ウィンドウで右クリックし、**変数**フォルダーをクリック**新しい変数**します。  
  
     **変数**が折りたたまれている場合、フォルダーを展開し、新しい変数を追加します。  
  
2.  [プロパティ] ウィンドウで、Identifier プロパティの名前を入力して変数を名前します。  
  
3.  .NET クラスなどの型の変数を関連付けます。  
  
    > [!NOTE]
    >  **型**ドロップダウン リストには、次の定義済み変数の型が含まれています:**ブール**、**バイト**、 **datetime**、 **10 進**、**二重**、 **int16**、 **int32**、 **int64**、 **sbyte**、**単一**、**文字列**、 **timespan**、 **uint16**、 **uint32**、および**uint64**します。 選択して、.NET データ型とクラスをアクセスすることができますも **\<.NET クラス.\>** が表示されます、**成果物の種類の選択** ダイアログ ボックス。  
  
4.  定義済み変数の型を選択した場合、変数の初期値を指定するオプションがあります。 [プロパティ] ウィンドウで次のように設定します。、**初期値**プロパティ。  
  
     それ以外の場合、選択した型が .NET クラスの場合は、既定のコンス トラクターを使用するオプションがあります。 [プロパティ] ウィンドウでは、次のプロパティを設定します。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |**既定のコンス トラクターを使用して、**|.NET クラスの既定のコンス トラクターがある場合、このプロパティは、最初に変数を使用するときに既定のコンス トラクターが呼び出されるかどうか決定します。<br /><br /> True-既定のコンス トラクターが呼び出されます。 これは、既定のコンス トラクターが使用可能な場合の既定値です。<br /><br /> False: 既定のコンス トラクターは呼び出されません。式でコンス トラクターを呼び出すか、オーケストレーションで使用する前に、変数への代入を行う必要があります。|  
  
    > [!NOTE]
    >  既定のコンス トラクターは、入力パラメーターを必要とする場合は設定できます**既定コンス トラクターを使用**に**False**をからコンス トラクターを呼び出して、**割り当て**; 図形の例では、`myVariable = myNamespace.myClass (param1, param2)`します。  
  
    > [!NOTE]
    >  完全に定義する前に、オーケストレーションに変数を追加するときに、オーケストレーション内の感嘆符が表示されます。 完全に定義して、感嘆符は、オーケストレーションが表示前に、この変数を削除する場合は、作成して、オーケストレーションのパラメーターを削除し、これらの感嘆符を削除するオーケストレーションを強制できます。  
  
### <a name="to-remove-a-variable"></a>変数を削除するには  
  
-   オーケストレーションの種類 ウィンドウで、クリックして削除する変数を右クリックして**削除**します。