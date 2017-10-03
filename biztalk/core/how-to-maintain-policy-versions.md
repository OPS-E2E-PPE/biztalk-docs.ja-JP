---
title: "ポリシー バージョンを管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c73b3575ec484ab611fccac920cef6d96d3800
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-policy-versions"></a>ポリシー バージョンを管理する方法
ルールをポリシーのバージョンに追加することにより、将来の開発に備えて特定のバージョンをルール ストアに保存できます。また、そのバージョンを公開して、厳密に定義されたルールのセットを作成し、これらのルールをルール ベースのアプリケーション用に展開することができます。  
  
 このトピックでは、次の操作の手順について説明します。  
  
-   ポリシーの空のバージョンを新規作成するには  
  
-   ポリシーのバージョンを保存するには  
  
-   ポリシーのバージョンを公開するには  
  
-   ポリシーの更新されたバージョンを作成するには  
  
-   ポリシーを更新して更新済みアセンブリを使用するには  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a>ポリシーの空のバージョンを新規作成するには  
  
-   ポリシー フォルダーを右クリックし、をクリックして**新しいバージョンの追加**です。  
  
### <a name="to-save-a-policy-version"></a>ポリシーのバージョンを保存するには  
  
-   ポリシーのバージョンを右クリックし、をクリックして**保存**です。  
  
### <a name="to-publish-a-policy-version"></a>ポリシーのバージョンを公開するには  
  
-   ポリシーのバージョンを右クリックし、をクリックして**発行**です。  
  
### <a name="to-create-an-updated-version-of-a-policy"></a>ポリシーの更新されたバージョンを作成するには  
  
1.  既存のポリシーのバージョンを右クリックし、をクリックして**コピー**です。  
  
2.  ポリシー フォルダーを右クリックし、をクリックして**貼り付け**です。  
  
     コピー元と同じ要素を持つ新しいバージョンが作成されます。  
  
    > [!NOTE]
    >  ポリシーが .NET アセンブリを使用する場合に、そのアセンブリが更新されているときは、ポリシーをアセンブリの新しいバージョンにバインドする必要があります。  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a>ポリシーを更新して更新済みアセンブリを使用するには  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、 をポイント**.NET Framework 構成**、クリックして**アセンブリの構成**.  
  
2.  ターゲット アセンブリのプロパティに移動し、**バインド ポリシー**タブです。  
  
3.  グローバル アセンブリ キャッシュで、バージョン番号を新しいバージョンに変更します。  
  
    > [!NOTE]
    >  ポリシーが使用するアセンブリはすべて、グローバル アセンブリ キャッシュに追加されている必要があります。