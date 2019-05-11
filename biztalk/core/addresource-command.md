---
title: AddResource コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d8831cbac23343186eb4df9959378cb49fe279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360202"
---
# <a name="addresource-command"></a>AddResource コマンド
このセクションのトピックでは、AddResource コマンドのパラメーターに関する参照情報を提供します。 このコマンドで使用するパラメーターを追加するアイテムの種類によって異なります。 成果物の種類の完全な一覧を取得する、 **ListTypes** 」の説明に従って、コマンド[ListTypes コマンド](../core/listtypes-command.md)します。  
  
 に特定の成果物の種類の追加のヘルプを取得するには、次のコマンドを入力します。  
  
 **BTSTask AddResource/Type:**\<*型名*\> **/でしょうか。**  
  
> [!NOTE]
>  追加するアイテムがあるファイル名を含む非常に長いパス名をアプリケーションにアイテムを追加する操作が表示される場合があります。 パスは 260 文字を超えることはできません。  
>   
>  追加操作が失敗した場合、操作中に実行されたすべてのアクションはロールバックする点を除いて、このコマンドでは、追加された場合にすべてのエントリが加えられた場合、エントリは Windows レジストリから削除されませんアセンブリはグローバル アセンブリ キャッシュから削除されません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AddResource コマンド:BizTalk アセンブリ](../core/addresource-command-biztalk-assembly.md)  
  
-   [AddResource コマンド:BizTalk バインド](../core/addresource-command-biztalk-binding.md)  
  
-   [AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)  
  
-   [AddResource コマンド:BAM アイテム](../core/addresource-command-bam-artifact.md)  
  
-   [AddResource コマンド:証明書](../core/addresource-command-certificate.md)  
  
-   [AddResource コマンド:COM コンポーネント](../core/addresource-command-com-component.md)  
  
-   [AddResource コマンド:ファイル](../core/addresource-command-file.md)  
  
-   [AddResource コマンド:処理前のスクリプト](../core/addresource-command-preprocessing-script.md)  
  
-   [AddResource コマンド:処理後のスクリプト](../core/addresource-command-postprocessing-script.md)  
  
-   [AddResource コマンド:ポリシー](../core/addresource-command-policy.md)  
  
-   [AddResource コマンド:仮想ディレクトリ](../core/addresource-command-virtual-directory.md)