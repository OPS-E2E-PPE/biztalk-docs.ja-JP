---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: true
ROBOTS: NOINDEX
title: Visual Studio Team Services への BizTalk Server アプリケーションの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: 4
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: a5ab2e23c4ccca6154334af234acdbd3f1847b26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360979"
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a>Visual Studio Team Services への BizTalk Server アプリケーションを追加します。
追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] vsts 継続的インテグレーションを使用してを自動的にデプロイするプロジェクト。  

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、自動的にするようにアプリケーションをデプロイすることができます、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Visual Studio Team Services (VSTS) を使用する環境。 

このトピックは、概要し、Visual Studio からソリューションを配置する主な手順を一覧表示、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 

## <a name="prerequisites"></a>前提条件
* インストール[Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* [ステップ 3:ビルドとリリース定義を作成します。](../core/feature-pack-add-build-release-definitions.md)
* 知識と経験 Git と Visual Studio でリポジトリを使用します。 新しいリポジトリとバージョン管理する場合は、これらの優れたリソースがあります。 

    [Git についての情報します。](https://www.visualstudio.com/learn-git/)  
    [Git と Team Services](https://www.visualstudio.com/docs/git/overview)
* 知識と経験で BizTalk プロジェクトでの作業 [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]

## <a name="add-biztalk-project-to-vsts"></a>BizTalk プロジェクトを VSTS に追加します。
1. **Visual Studio**への接続、**ソース リポジトリ**、および**複製**コンピューターにします。
2. 開くか作成、 **BizTalk プロジェクト**(.btproj)。

   > [!NOTE]
   > 複数のプロジェクトは、同じソリューションに追加できます。
   
3. 新しい追加**アプリケーション用の BizTalk Server プロジェクト**(.btaproj)。
4. プロジェクトを右クリックし、**ソリューション エクスプ ローラー**、選択および**プロパティ**します。
5. 構成、**バージョン**への接続プロパティと、 **Visual Studio Team Services**アカウント。

    ![Visual Studio 構成 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. すべてのアセンブリとアプリケーションに必要なアイテムを追加します。
7. 更新プログラム、 **binding.xml**正しいバインド情報を含むファイル。
8. 更新プログラム、 **BizTalkServerInventory.json**にインストールされる成果物を正しい順序ですべての成果物を[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。
9. 右クリックし、**ビルド**エラーの有無を確認するソリューションです。 
10. ビルドが正常に完了すると、ソリューションを右クリックし **デプロイ**します。
11. アプリケーションに自動的にデプロイする必要があります、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。

## <a name="see-also"></a>関連項目
[Feature Pack を構成します。](../core/configure-the-feature-pack.md)