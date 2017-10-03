---
title: "既存のリンクを管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e61bc8c7fbf015eba28666c63dbeabf57a39e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-existing-links"></a>既存のリンクを管理する方法
リンクの送信元や送信先の変更、リンクの名前付けや名前の変更、およびリンクの削除などが必要になる場合があります。 このトピックでは、このようなリンクに関する操作を実行する手順について説明します。  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a>リンクの送信元または送信先を変更するには  
  
1.  BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。  
  
     グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。  
  
2.  リンクのいずれかのエンドポイントを、新たに接続するスキーマ ノードまたは Functoid にドラッグします。  
  
     エンドポイントをドラッグしている間は、カーソルが十字型になります。 リンクを受け付けることができないスキーマ ノードや Functoid (またはその他のオブジェクト) にドラッグすると、円の中に 1 本の線が描かれた形にカーソルが変化します。  
  
    > [!IMPORTANT]
    >  2 つ以上の入力リンクを 1 つの Functoid に接続して、これらの入力リンクのいずれかを送信元スキーマの他のノードまたは他の Functoid にリダイレクトする場合、元の Functoid に対する入力パラメーターの順序は維持されません。 使用して、**構成\<Functoid > Functoid**  ダイアログ ボックスを入力パラメーターの順序を確認し、必要に応じて順序を変更します。 Functoid の入力パラメーターの順序変更の詳細については、次を参照してください。 [Functoid プロパティの編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。  
  
### <a name="to-setedit-the-label-of-a-link"></a>リンクのラベルを設定/編集するには  
  
1.  BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。  
  
     グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを使用して、リンクの (新しい) の名前を指定、**ラベル**プロパティです。  
  
### <a name="to-delete-a-link"></a>リンクを削除するには  
  
1.  BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。  
  
     グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。  
  
2.  **編集** メニューのをクリックして**削除**です。  
  
     DEL キーを押してまたはリンクを右クリックしてをクリックして**削除**ショートカット メニューの します。  
  
    > [!NOTE]
    >  複数のリンクおよび Functoid を一括で選択し、1 つの操作でそれらを削除できます。 リンクや Functoid の一括削除を取り消したり、やり直したりできます。 詳細については、元に戻すおよびやり直し操作を参照してください。[を元に戻すまたはユーザーの操作を再実行する方法](../core/how-to-undo-or-redo-user-operations.md)です。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定してフィールドのマッピング](../core/using-links-to-specify-record-and-field-mappings.md)