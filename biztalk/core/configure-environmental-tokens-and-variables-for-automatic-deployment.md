---
title: 環境のトークンと変数を作成 |Microsoft ドキュメント"
description: 環境のトークンを使用するバインド ファイルを更新し、BizTalk Server アプリケーションの展開を自動化する VSTS で変数を作成
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
ms.openlocfilehash: 6d84fa393410e3084c87e762140530a45b0b78b5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054570"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>環境のトークンと自動展開用の変数を構成します。
Visual Studio Team Services (VSTS) の変数を使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルです。

## <a name="overview"></a>概要
環境では、VSTS は、変数を追加したり、値に設定します。 たとえば、作成することができます、 *sendPortPath*変数で物理フォルダーにその値を設定、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

内で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]アプリケーション バインド ファイル、構成可能な変数できます受信場所の名前などの XML タグ内で何もするホスト、送信ポート、URI に表示され、します。 

これらの変数は、VSTS の環境に固有であり、同じアプリケーションを複数の展開に使用できる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 

VSTS 内の変数を作成する方法と、バインド ファイルに、VSTS 変数を追加する方法を説明します。 

## <a name="add-variables-to-the-binding-file"></a>バインド ファイルに変数を追加します。

1. アプリケーションのバインド ファイルを開きます。

    ![バインド ファイルを開く](../core/media/biztalk-feature-pack-1-binding-1.png)

2. 変更する要素を検索します。

    ![要素を選択します。](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. 設定済みの値を削除して、変数で置き換えます:`$(YourValue)`です。 たとえば、入力`$(SendPort1)`: 

    ![バインド ファイル](../core/media/biztalk-feature-pack-1-binding-3.png)

4. 完了したら、バインド ファイルを保存し、JSON のビルド テンプレートに追加 (ステップの[手順 1: アプリケーションの追加の更新 (&)、プロジェクトの .json テンプレート](feature-pack-add-application-project.md))。

## <a name="create-the-variables-in-vsts"></a>VSTS で変数を作成します。

1. VSTS アカウントに次のように選択します。**ビルドとリリースの**、を選択して**リリース**です。

2. 選択、**リリース定義**を選択して**変数**:  

    ![バインド ファイル](../core/media/vsts-release-variables.png)

3. 選択**追加**、変数の名前と値を作成します。   

    ![変数を構成します。](../core/media/environment-specific-variables.png)

4. **保存**変更します。 展開が開始されると、値は、バインド ファイルから追加されます。

## <a name="see-also"></a>参照
[Visual Studio Team Services の自動展開を構成します。](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[Feature Pack の構成](configure-the-feature-pack.md)