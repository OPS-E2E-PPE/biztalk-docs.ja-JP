---
title: マップの管理 |Microsoft ドキュメント
description: リンクを表示するマップを削除するなど、BizTalk server マップに関する作業を
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
ms.openlocfilehash: 9c86a1cd23fe8f06c2671be163409cd405e9cbe1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263130"
---
# <a name="manage-maps"></a>マップを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールを使用してマップを管理する方法について説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、マップを使用して、あるスキーマのレコードとフィールドを別のスキーマのレコードとフィールドに変換します。 マップは、オーケストレーション、送信ポート、および受信ポートで使用されることがあります。  

## <a name="add-maps-to-an-application"></a>アプリケーションにマップを追加します。  
 マップは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。 マップを単独でアプリケーションに追加することはできません。マップは次のようにしてアプリケーションに追加されます。  
  
-   」の説明に従って、アプリケーションにマップを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。  
  
-   」の説明に従って、マップを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
-   開発者が展開したときに、アプリケーションからマップを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  
  
 マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。 マップを作成する方法の詳細については、次を参照してください。[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)です。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順 
  
-   [アプリケーションのマップを表示します。](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [アプリケーションから、マップを削除します。](../core/how-to-remove-a-map-from-an-application.md)