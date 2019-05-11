---
title: 環境トークンと変数の作成 |Microsoft Docs"
description: 環境のトークンを使用するバインド ファイルを更新して、BizTalk Server アプリケーションの展開を自動化する VSTS での変数を作成
ms.custom: ''
ms.date: 11/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: 4
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d3af4817e2974d1196fb08acf94195b997b0c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356434"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>環境トークンと自動展開用の変数を構成します。
Visual Studio Team Services (VSTS) の変数を使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイル。

## <a name="overview"></a>概要
VSTS 環境では、変数を追加し、それらの値に設定します。 たとえば、作成、 *sendPortPath*変数で、物理フォルダーにその値を設定、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

内で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]アプリケーションのバインド ファイル、構成可能な変数受信場所の名前などの XML タグ内のすべて、ホスト、送信ポート、URI でき具合です。 

これらの変数は、VSTS の環境に固有であり、同じアプリケーションを複数のデプロイに使用できる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 

紹介する VSTS 内の変数を作成する方法と、バインド ファイルに、VSTS の変数を追加する方法。 

## <a name="add-variables-to-the-binding-file"></a>変数をバインド ファイルに追加します。

1. アプリケーションのバインド ファイルを開きます。

    ![バインド ファイルを開く](../core/media/biztalk-feature-pack-1-binding-1.png)

2. 変更する要素を検索するには。

    ![要素を選択します。](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. 設定の値を削除し、変数で置き換えます:`$(YourValue)`します。 たとえば、入力`$(SendPort1)`: 

    ![バインド ファイル](../core/media/biztalk-feature-pack-1-binding-3.png)

4. 完了したら、バインド ファイルを保存し、JSON のビルド テンプレートに追加 (手順[手順 1。アプリケーションの追加のプロジェクトと更新プログラムの .json テンプレート](feature-pack-add-application-project.md))。

## <a name="create-the-variables-in-vsts"></a>VSTS での変数を作成します。

1. VSTS アカウントに次のように選択します。**ビルドとリリース**、を選択し**リリース**します。

2. 選択、**リリース定義**、選び**変数**:  

    ![バインド ファイル](../core/media/vsts-release-variables.png)

3. 選択**追加**、変数の名前と値を作成します。   

    ![変数を構成します。](../core/media/environment-specific-variables.png)

4. **保存**変更します。 デプロイが開始されると、バインド ファイルから値が追加されます。

## <a name="see-also"></a>関連項目
[Visual Studio Team Services での自動展開を構成します。](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[Feature pack を構成します。](configure-the-feature-pack.md)