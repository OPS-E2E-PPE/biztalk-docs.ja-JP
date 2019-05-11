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
ms.openlocfilehash: db8ea58b62537d26b8bc088d84eefa6186dc8941
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348356"
---
# <a name="error---functoid-has-no-input"></a>エラー - Functoid に入力がありません。
**エラー コード**  

 btm1012  

 **説明**  

 対象の functoid には、少なくとも 1 つの入力パラメーターが必要ですが、入力パラメーターが指定されていません。  

 **ユーザーの操作**  

 入力パラメーターの予想される順序に特に注意してください、対象の functoid の入力パラメーターの適切な数を提供するのに、次のメソッドの一方または両方を使用します。  

- ドラッグすると、送信元スキーマまたはマップのグリッド ページで、対象の functoid の左側にある他の functoid の出力で、対象の functoid といずれかのノード間のリンクを作成します。  

- 対象の functoid を選択し、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成して、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 定数入力パラメーターの作成、指定された値、およびこのダイアログ ボックスで、その他の入力パラメーターを基準とした適切な順序で配置できます。
