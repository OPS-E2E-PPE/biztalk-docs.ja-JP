---
title: "環境のトークンと自動展開用の変数の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7d148f79fceb68b24feb45882ab89767369ed7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>環境のトークンと自動展開用の変数を構成します。
Visual Studio Team Services (VSTS) の変数を使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルです。

## <a name="overview"></a>概要
環境では、VSTS は、変数を追加したり、値に設定します。 たとえば、作成することができます、 *sendPortPath*変数で物理フォルダーにその値を設定、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

内で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]アプリケーション バインド ファイル、構成可能な変数できます受信場所の名前などの XML タグ内で何もするホスト、送信ポート、URI に表示され、します。 

これらの変数は、VSTS の環境に固有であり、同じアプリケーションを複数の展開に使用できる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 

このトピックでは、VSTS ファイル内の変数、バインディング、および VSTS 内の変数を作成する方法追加する方法を示します。 

## <a name="configure-the-variables-in-your-biztalk-binding-file"></a>BizTalk バインド ファイル内の変数を構成します。

次の例の一部、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルの場合は、トークンを適用する方法を示しています。

1. アプリケーションのバインド ファイルを開きます。

    ![BizTalk Feature Pack 1 をバインド 1](../core/media/biztalk-feature-pack-1-binding-1.png)

2. 変更する要素を検索します。

    ![BizTalk Feature Pack 2 をバインド 1](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. 設定済みの値を削除して、変数で置き換えます:`$(YourValue)`です。 たとえば、入力`$(SendPort1)`: 

    ![BizTalk Feature Pack 1 が 3 のバインド](../core/media/biztalk-feature-pack-1-binding-3.png)


4. 終了したら、バインド ファイルを保存し、JSON ビルド テンプレートに適用します。
5. Visual Studio チーム サービス、ソリューションにサインインし、選択**ビルドし、リリースの**します。
6. 移動して**リリース**です。 選択、**リリース定義**、新規に作成します。
7. **環境****新しい環境を追加**、または既存の環境に変更します。 

    ![新しい環境を追加します。](../core/media/add-a-new-environment.png)

8. 省略記号ボタンをクリックし、選択**変数構成**:

    ![変数を構成します。](../core/media/configure-variables.png)

9. バインド ファイルに作成されたトークンの名前を使用して、各環境の変数を追加することで、値が異なる複数の環境にアプリケーションを展開できます。

    ![特定の環境変数](../core/media/environment-specific-variables.png)
    
10. 選択**OK**を新しい変数を保存します。
11. ビルドが開始されると、値は、バインド ファイルから追加されます。

## <a name="next-step"></a>次の手順
[VSTS を BizTalk アプリケーションを追加します。](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)