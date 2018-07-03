---
title: エラー - Functoid の固定入力が一致しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functoidFixedInputMismatch
ms.assetid: d235e7c3-efcf-4128-aef7-cdfdf1f317be
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85f9158bc7c648da5a70f19e3b8b48e6c6f7294a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017910"
---
# <a name="error---functoid-fixed-input-mismatch"></a>エラー - Functoid の固定入力が一致しません
**エラー コード**  

 btm1010  

 **説明**  

 Functoid に指定されている入力パラメーターの数が正しくありません。 入力パラメーターの数は指定したものと同一である必要があります。  

 **ユーザーの操作**  

 次の方法の 1 つ以上を使用して、Functoid に、表示されている数の入力パラメーターを指定します。その際、想定されている入力パラメーターの順序に特に注意してください。  

- リンクを追加するには、送信元スキーマまたは他の Functoid の出力のいずれかのノードと対象の Functoid の間をドラッグしてリンクを作成します。他の Functoid とは、マップ グリッド ページで対象の Functoid の左側に表示されている Functoid を指します。  

- その他のリンクを作成する対象の functoid を選択、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成して、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 このダイアログ ボックスでは、定数入力パラメーターを作成して値を設定し、他の入力パラメーターを考慮したうえで適切な順序に配置できます。  

- リンクごとに、対象の functoid の左側に接続されている既存のリンクを削除するリンクを右クリックし をクリックし、**削除**します。  

- 既存のリンクを削除、対象の functoid を選択し、省略記号をクリックする (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、し、**構成\<Functoid\> Functoid**ダイアログ ボックスで、削除を選択すると、クリックして入力パラメーターはすべて、 ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。 定数入力パラメーターを削除する場合は、この方法を使用する必要があります。
