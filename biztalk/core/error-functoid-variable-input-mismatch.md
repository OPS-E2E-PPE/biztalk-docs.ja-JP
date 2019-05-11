---
title: エラー - Functoid 変数の入力が一致しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functoidVariableInputMismatch
ms.assetid: fda3066b-d0de-4f61-b78f-4726f6796e1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed171944d3d9e9dbb0de5b4c030ddc1af21ae8a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389083"
---
# <a name="error---functoid-variable-input-mismatch"></a>エラー - Functoid 変数の入力が一致しません
**エラー コード**  

 btm1011  

 **説明**  

 対象の functoid には、指定された入力パラメーターの正しい数はありません。 入力パラメーターの数は、指定した範囲内にある必要があります。  

 **ユーザーの操作**  

 1 つ以上の入力パラメーターの予想される順序に特に注意してください、対象の functoid の入力パラメーターの指定された数を指定する次のメソッドを使用します。  

- その他のリンクを作成するには、送信元スキーマまたはマップのグリッド ページで、対象の functoid の左側にある他の functoid の出力で、対象の functoid といずれかのノード間のリンクを作成するドラッグします。  

- その他のリンクを作成する対象の functoid を選択、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成して、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 定数入力パラメーターの作成、指定された値、およびこのダイアログ ボックスで、その他の入力パラメーターを基準とした適切な順序で配置できます。  

- リンクごとに、対象の functoid の左側に接続されている既存のリンクを削除するリンクを右クリックし をクリックし、**削除**します。  

- 既存のリンクを削除、対象の functoid を選択し、省略記号をクリックする (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、し、**構成\<Functoid\> Functoid**ダイアログ ボックスで、削除を選択すると、クリックして入力パラメーターはすべて、 ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。 このメソッドを使用して、定数入力パラメーターを削除する必要があります。
