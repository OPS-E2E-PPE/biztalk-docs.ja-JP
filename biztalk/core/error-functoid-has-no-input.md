---
title: エラー - Functoid に入力がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functiodHasNoInput
ms.assetid: ea59b902-953d-4a5f-aa28-dbaa0a017dca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fd2626d0b3332ddbf2def47502e7b323a0ae0e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000779"
---
# <a name="error---functoid-has-no-input"></a>エラー - Functoid に入力がありません。
**エラー コード**  

 btm1012  

 **説明**  

 Functoid には少なくとも 1 つの入力パラメーターが必要ですが、入力パラメーターが指定されていません。  

 **ユーザーの操作**  

 次のうちの 1 つまたは両方の方法を使用して、Functoid に適切な数の入力パラメーターを指定します。その際、想定されている入力パラメーターの順序に特に注意してください。  

- 送信元スキーマまたは他の Functoid の出力のいずれかのノードと対象の Functoid の間でドラッグしてリンクを作成します。他の Functoid とは、マップ グリッド ページで対象の Functoid の左側に表示されている Functoid を指します。  

- 対象の functoid を選択し、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成して、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 このダイアログ ボックスでは、定数入力パラメーターを作成して値を設定し、他の入力パラメーターを考慮したうえで適切な順序に配置できます。
