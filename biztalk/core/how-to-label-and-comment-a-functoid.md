---
title: Functoid、ラベルし、コメントする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db30ca1b7bee06c633245e05808ad521b27e51d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384863"
---
# <a name="how-to-label-and-comment-a-functoid"></a>Functoid、ラベルし、コメントする方法
ラベルとコメントは、functoid またはマップ内のリンクの目的を文書化に役立ちます。 使用することができます、**ラベル**functoid の名前を指定するプロパティ。 **コメント**プロパティでは、通常に関連することによって実行される操作について、functoid に関する追加情報を提供することができます。  
  
 次の図は、ラベルと、functoid のコメントを示します。 Functoid は、送信元スキーマから 2 つの入力 (Field1 と Field3) を追加し、ターゲット スキーマの Field4 に結果を出力します。 この例では、functoid のラベルは"Add Field1 and Field3"とコメントが"The addition is an output to Field4"。  
  
 ![Functoid のラベルとコメントを挿入する](../core/media/label.gif "Label_")  
  
 非常に複雑なマッピングの一部の functoid を使用できる、ので、適切にラベルと関連するコメントを提供する重要なは。 ラベルの functoid およびリンクの両方を指定できます。 リンクのラベル付けする方法については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)します。  
  
 ラベルおよび functoid のコメントを次のようにできます。  
  
-   使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックス。  
  
-   使用して、**プロパティ**ウィンドウ。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a>ラベルとコメントの構成 ダイアログ ボックスから functoid を  
  
1.  Functoid のラベルとコメントをクリックしたを右クリックして**Functoid 入力の構成**します。  
  
2.  **構成\<Functoid\> Functoid**ダイアログ ボックスで、をクリックして、**ラベルとコメント**タブ。  
  
3.  次の情報を入力し、クリックして**OK**します。  
  
    -   **ラベル –** 新しい名前を入力します。  
  
        > [!IMPORTANT]
        >  許可される文字の最大数には 256 です。 数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りは破棄されます。  
  
    -   **コメント –** functoid のコメントを入力します。  
  
        > [!IMPORTANT]
        >  許可される文字の最大数は、1024 です。 1,024 個を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りは破棄されます。  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a>ラベルとコメント プロパティ ウィンドウから functoid を  
  
1.  ラベルとコメント functoid を選択します。  
  
2.  **プロパティ**ウィンドウが、次の情報を入力し、クリックして**OK**します。  
  
    -   **ラベル –** 新しい名前を入力します。  
  
        > [!IMPORTANT]
        >  許可される文字の最大数には 256 です。 数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りは破棄されます。  
  
    -   **コメント –** functoid のコメントを入力します。  
  
        > [!IMPORTANT]
        >  許可される文字の最大数は、1024 です。 1,024 個を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りは破棄されます。  
  
## <a name="see-also"></a>参照  
 [Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md)