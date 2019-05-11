---
title: BizTalk アセンブリの管理 |Microsoft Docs
description: BizTalk server の追加、更新、依存関係を表示する、アセンブリの削除を含むアセンブリを使用した作業へのリンク
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62cc92f5-a1ea-46e4-88e6-b8a71a0c40a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5657484f45c7426b8f51e8ef1258c2d0d62a4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328764"
---
# <a name="manage-biztalk-assemblies"></a>BizTalk アセンブリを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk グループに BizTalk アセンブリを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk アセンブリを管理する方法について説明します。 BizTalk アセンブリは、オーケストレーション、パイプライン、スキーマ、マップなど、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションで使用するリソース情報を集めて格納した Microsoft Windows の DLL ファイルです。 BizTalk アセンブリの背景については、次を参照してください。 [BizTalk アセンブリ](../core/biztalk-assemblies.md)します。  
  
> [!IMPORTANT]
>  プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。 プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。 イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。 (展開に関してイベント ログに生成されるメッセージ。"User"{1}「アセンブリの展開」{0}「プロパティのスキーマを格納します」。 展開解除は、イベント ログに記録されるメッセージは次のとおりです。"User"{1}「アセンブリの展開を解除」{0}「プロパティのスキーマを格納します」)。  
> 
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 開発者は、使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、BizTalk アセンブリを開発する[BizTalk Server アプリケーションの開発](../core/developing-biztalk-server-applications.md)からそれらを配置できますと[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って[を展開します。Visual Studio から BizTalk アセンブリを BizTalk アプリケーションに](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。 また、開発者は、このセクションで説明する管理コンソールを使用して、開発プロセス中に BizTalk アセンブリを管理できます。  
  
## <a name="next-steps"></a>次のステップ 
  
-   [BizTalk アセンブリをアプリケーションに追加する](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [BizTalk アセンブリの展開オプションを変更します。](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [BizTalk アセンブリの依存関係を表示する](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [アプリケーションから BizTalk アセンブリを削除する](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)