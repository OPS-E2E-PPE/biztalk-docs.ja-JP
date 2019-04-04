---
title: マップの管理 |Microsoft Docs
description: リンクを表示するマップを削除するなど、BizTalk Server のマップを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6957a4f3d73c5f59df5cd36f70a7ed34631fa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019832"
---
# <a name="manage-maps"></a>マップを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールを使用してマップを管理する方法について説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、マップを使用して、あるスキーマのレコードとフィールドを別のスキーマのレコードとフィールドに変換します。 マップは、オーケストレーション、送信ポート、および受信ポートで使用されることがあります。  

## <a name="add-maps-to-an-application"></a>マップをアプリケーションに追加します。  
 マップは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。 マップを単独でアプリケーションに追加することはできません。マップは次のようにしてアプリケーションに追加されます。  
  
- 」の説明に従って、アプリケーションに、マップを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
- 」の説明に従って、マップを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。  
  
- 開発者が展開したときに、アプリケーションからマップを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  
  
  マップの背景については、[マップ](../core/maps.md)を参照してください。 マップを作成する方法の詳細については、[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)を参照してください。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。
  
## <a name="next-steps"></a>次のステップ 
  
-   [アプリケーションのマップを表示する](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [マップをアプリケーションから削除する](../core/how-to-remove-a-map-from-an-application.md)