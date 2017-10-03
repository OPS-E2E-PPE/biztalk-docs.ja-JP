---
title: "Files3 のバインドのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- target computer, cleaning
- importing binding files
- cleaning target computer
ms.assetid: 955bb3e1-3dbc-43ce-9126-205d838ae662
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1d95c40e3e556068e15a269ee4cbb7e995429a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート
バインド ファイルをインポートする BizTalk Server を使用する前に、次の操作を確認します。  
  
-   CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。 新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。  
  
-   JD Edwards システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 詳細については、次を参照してください。[展開の制限事項](../core/deployment-limitations2.md)です。  
  
> [!NOTE]
>  展開には、受信場所の構成が上書きされます。 バインド ファイルとアセンブリを展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
## <a name="importing-the-binding-files"></a>バインド ファイルをインポートします。  
 バインド ファイルをインポートするには、次の手順を使用します。  
  
#### <a name="to-import-the-binding-files"></a>バインド ファイルをインポートするには  
  
1.  **開始** メニューのをポイント**Program Files**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**BizTalk Server 管理コンソールを開始します。  
  
2.  BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**の順に展開および**アプリケーション**です。  
  
3.  目的のアプリケーションを右クリックし、順にポイント**インポート**、順にクリック**バインド**です。  
  
4.  **バインドのインポート**ダイアログ ボックスで、参照し、バインド ファイルを選択してクリックして**開く**です。  
  
## <a name="cleaning-the-target-computer"></a>展開先のコンピューターのクリーニング  
 次の手順を使用して展開先のコンピューターをクリーニングします。  
  
#### <a name="to-clean-the-target-computer"></a>展開先のコンピューターをクリーニングするには  
  
-   送信ポートおよびオーケストレーションにバインドされている受信場所を削除します。  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld 送信ハンドラーの作成](../core/creating-jd-edwards-oneworld-send-handlers.md)   
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies4.md)