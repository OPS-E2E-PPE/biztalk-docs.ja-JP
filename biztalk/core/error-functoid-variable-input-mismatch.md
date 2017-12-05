---
title: "エラー - Functoid 変数の入力が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.functoidVariableInputMismatch
ms.assetid: fda3066b-d0de-4f61-b78f-4726f6796e1f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edb9268adccc3af652e4ac0f1087b231da2c8277
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---functoid-variable-input-mismatch"></a>エラー - Functoid 変数の入力が一致しません
**エラー コード**  
  
 btm1011  
  
 **説明**  
  
 Functoid に指定されている入力パラメーターの数が正しくありません。 入力パラメーターの数は、指定された範囲内である必要があります。  
  
 **ユーザーの操作**  
  
 次の方法の 1 つ以上を使用して、Functoid に、表示されている数の入力パラメーターを指定します。その際、想定されている入力パラメーターの順序に特に注意してください。  
  
-   リンクを追加するには、送信元スキーマまたは他の Functoid の出力のいずれかのノードと対象の Functoid の間をドラッグしてリンクを作成します。他の Functoid とは、マップ グリッド ページで対象の Functoid の左側に表示されている Functoid を指します。  
  
-   その他のリンクを作成する対象の functoid を選択して、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成してで、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 このダイアログ ボックスでは、定数入力パラメーターを作成して値を設定し、他の入力パラメーターを考慮したうえで適切な順序に配置できます。  
  
-   対象の functoid の左側に接続されている各リンクについて、既存のリンクを削除するリンクを右クリックし、をクリックして**削除**です。  
  
-   既存のリンクを削除する、対象の functoid を選択し、省略記号ボタンをクリックする (**.**) に関連付けられたボタン、**入力パラメーター**プロパティに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウでし、**構成\<Functoid\> Functoid**ダイアログ ボックスで、削除を選択しをクリックしてすべての入力パラメーター、 ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。 定数入力パラメーターを削除する場合は、この方法を使用する必要があります。