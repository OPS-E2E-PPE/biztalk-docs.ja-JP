---
title: "ラベルを付けるし、Functoid のコメントを指定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fccdeefa35f9abb5a0c3158dba518d524811c611
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-label-and-comment-a-functoid"></a>Functoid にラベル付けする方法とコメントを追加する方法
ラベルとコメントは、マップの Functoid またはリンクの目的を文書化するのに役立ちます。 使用することができます、**ラベル**functoid の名前を指定するプロパティです。 **コメント**プロパティでは、によって実行される操作についての関連する通常、functoid に関する追加情報を提供することができます。  
  
 次の図では、Functoid のラベルとコメントを示します。 この Functoid は、送信元スキーマからの 2 つの入力 (Field1 と Field3) を追加し、ターゲット スキーマの Field4 に結果を出力します。 この例では、Functoid のラベルは "Add Field1 and Field3" で、コメントは "The addition is an output to Field4" です。  
  
 ![Functoid のラベルとコメントを挿入する](../core/media/label.gif "Label_")  
  
 Functoid は非常に複雑なマッピングの一部である場合があるので、適切なラベルを付け、関連するコメントも指定することが重要です。 Functoid とリンクの両方にラベルを指定できます。 リンクのラベルを付ける方法については、次を参照してください。[リンクのラベルを付ける方法](../core/how-to-label-a-link.md)です。  
  
 Functoid のラベルとコメントは次の方法で指定できます。  
  
-   使用して、**構成\<Functoid > Functoid**  ダイアログ ボックス。  
  
-   使用して、**プロパティ**ウィンドウです。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a>構成ダイアログ ボックスで Functoid のラベルとコメントを指定するには  
  
1.  Functoid のラベルとコメント、して、をクリックを右クリックして**Functoid 入力の構成**です。  
  
2.  **構成\<Functoid > Functoid**ダイアログ ボックスで、をクリックして、**ラベルとコメント**タブです。  
  
3.  次の情報を入力し、クリックして**OK**です。  
  
    -   **ラベル –**新しい名前を入力します。  
  
        > [!IMPORTANT]
        >  使用できる文字の最大数は 256 です。 数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りの部分は破棄されます。  
  
    -   **コメント –** functoid のコメントを入力します。  
  
        > [!IMPORTANT]
        >  使用できる文字の最大数は 1024 です。 1024 を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りの部分は破棄されます。  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a>[プロパティ] ウィンドウで Functoid のラベルとコメントを指定するには  
  
1.  ラベルとコメントを指定する Functoid を選択します。  
  
2.  **プロパティ**ウィンドウが、次の情報を入力し、クリックして**OK**です。  
  
    -   **ラベル –**新しい名前を入力します。  
  
        > [!IMPORTANT]
        >  使用できる文字の最大数は 256 です。 数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りの部分は破棄されます。  
  
    -   **コメント –** functoid のコメントを入力します。  
  
        > [!IMPORTANT]
        >  使用できる文字の最大数は 1024 です。 1024 を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りの部分は破棄されます。  
  
## <a name="see-also"></a>参照  
 [Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md)