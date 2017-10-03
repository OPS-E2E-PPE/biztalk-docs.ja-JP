---
title: "AddResource コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d2cb07bd0a05ddd1e79f4048bfe30e51e8d866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command"></a>AddResource コマンド
このセクションの各トピックでは、AddResource コマンドの各種パラメーターについてのリファレンス情報を紹介しています。 このコマンドで使用されるパラメーターは、追加するアイテムの種類によって異なります。 成果物の種類の完全な一覧を取得するを使用して、 **ListTypes**コマンドを」の説明に従って[ListTypes コマンド](../core/listtypes-command.md)です。  
  
 次のコマンドを入力することによって、追加するアイテムの種類に応じたヘルプを参照できます。  
  
 **BTSTask AddResource/Type:**\<*型名*> **/しますか?**  
  
> [!NOTE]
>  追加するアイテムのパス名 (あるいはファイル名) が極端に長いと、アイテムをアプリケーションに追加するときにエラーが発生する場合があります。 パスは 260 文字を超えることはできません。  
>   
>  追加操作に失敗した場合、その操作中に行われたすべてのアクションがロールバックされます。ただし、このコマンドでグローバル アセンブリ キャッシュに追加されたアセンブリは削除されず、そのまま残ってしまいます。また、Windows レジストリにエントリが書き込まれた場合も、エントリは削除されません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AddResource コマンド: BizTalk アセンブリ](../core/addresource-command-biztalk-assembly.md)  
  
-   [AddResource コマンド: BizTalk バインド](../core/addresource-command-biztalk-binding.md)  
  
-   [AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)  
  
-   [AddResource コマンド: BAM アイテム](../core/addresource-command-bam-artifact.md)  
  
-   [AddResource コマンド: 証明書](../core/addresource-command-certificate.md)  
  
-   [AddResource コマンド: COM コンポーネント](../core/addresource-command-com-component.md)  
  
-   [AddResource コマンド: ファイル](../core/addresource-command-file.md)  
  
-   [AddResource コマンド: 前処理スクリプト](../core/addresource-command-preprocessing-script.md)  
  
-   [AddResource コマンド: 処理後のスクリプト](../core/addresource-command-postprocessing-script.md)  
  
-   [AddResource コマンド: ポリシー](../core/addresource-command-policy.md)  
  
-   [AddResource コマンド: 仮想ディレクトリ](../core/addresource-command-virtual-directory.md)