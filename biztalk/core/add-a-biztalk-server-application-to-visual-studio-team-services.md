---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: True
ROBOTS: NOINDEX
title: "Visual Studio Team Services への BizTalk Server アプリケーションの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 1a6b7ba32c0077b3df107b00525bb34ef011e483
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a>Visual Studio Team Services への BizTalk Server アプリケーションを追加します。
追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] VSTS 継続的インテグレーションを使用して自動的に展開するプロジェクトです。  

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、するようにアプリケーションを自動的に展開することができます、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を Visual Studio Team Services (VSTS) を使用する環境です。 

このトピックでは、概要を説明し、Visual Studio からソリューションを展開する主な手順を一覧表示、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

## <a name="prerequisites"></a>前提条件
* インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* [手順 3: ビルドの作成し、定義のリリース](../core/feature-pack-add-build-release-definitions.md)
* 知識と経験 Git と Visual Studio でリポジトリを使用します。 新しいリポジトリとバージョン管理する場合は、これら優れたリソースがあります。 

    [Git を説明します。](https://www.visualstudio.com/learn-git/)  
    [Git および Team Services](https://www.visualstudio.com/docs/git/overview)
* 知識と経験に BizTalk プロジェクトの操作[!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]

## <a name="add-biztalk-project-to-vsts"></a>VSTS を BizTalk プロジェクトを追加します。
1. **Visual Studio**への接続、**ソース リポジトリ**、および**クローン**コンピューターにします。
2. 開くか作成、 **BizTalk プロジェクト**(.btproj)。

   > [!NOTE]
   > 複数のプロジェクトは、同じソリューションに追加できます。
   
3. 新しい**アプリケーション用の BizTalk Server プロジェクト**(.btaproj)。
4. プロジェクトを右クリックし、**ソリューション エクスプ ローラー**を選択して**プロパティ**です。
5. 構成、**バージョン**と接続プロパティを**Visual Studio Team Services**アカウント。

    ![Visual Studio 構成 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. すべてのアセンブリと、アプリケーションで必要な成果物を追加します。
7. 更新プログラム、 **binding.xml**正しいバインド情報を含むファイルです。
8. 更新プログラム、 **BizTalkServerInventory.json** 、すべての成果物、およびにインストールされている成果物用に正しい順序で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。
9. 右クリックし、**ビルド**ソリューションのすべてのエラーを確認します。 
10. ビルドが正常に完了すると、ソリューションを右クリックし **展開**です。
11. 自動的に展開する必要があります、アプリケーション、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。

## <a name="see-also"></a>参照
[この機能パックを構成します。](../core/configure-the-feature-pack.md)