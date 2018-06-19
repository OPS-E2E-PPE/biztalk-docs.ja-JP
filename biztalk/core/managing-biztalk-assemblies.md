---
title: BizTalk アセンブリの管理 |Microsoft ドキュメント
description: BizTalk Server で、追加、更新、依存関係の表示、およびアセンブリの削除を含むアセンブリと共に動作へのリンク
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
ms.openlocfilehash: 8c0dc8e74e23c7dc0b3a4e7a62a76297988b6b2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262690"
---
# <a name="manage-biztalk-assemblies"></a>BizTalk アセンブリを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk グループに BizTalk アセンブリを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk アセンブリを管理する方法について説明します。 BizTalk アセンブリは、オーケストレーション、パイプライン、スキーマ、マップなど、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションで使用するリソース情報を集めて格納した Microsoft Windows の DLL ファイルです。 BizTalk アセンブリの背景情報については、次を参照してください。 [BizTalk アセンブリ](../core/biztalk-assemblies.md)です。  
  
> [!IMPORTANT]
>  プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。 プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。 イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。 (展開に関してイベント ログに生成されるメッセージ:「ユーザー「{1}」には、"{0}"プロパティのスキーマを含んでいるアセンブリが展開されている」です。 展開解除に関してイベント ログに生成されるメッセージ:「「{1}」ユーザーは、"{0}"プロパティのスキーマを含んでいるアセンブリを展開解除」です)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 開発者は、使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、BizTalk アセンブリを開発する[BizTalk Server アプリケーションの開発](../core/developing-biztalk-server-applications.md)からに展開できると[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って[を展開します。BizTalk アプリケーションに Visual Studio から BizTalk アセンブリ](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。 また、開発者は、このセクションで説明する管理コンソールを使用して、開発プロセス中に BizTalk アセンブリを管理できます。  
  
## <a name="next-steps"></a>次の手順 
  
-   [BizTalk アセンブリをアプリケーションに追加します。](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [BizTalk アセンブリの展開オプションを変更します。](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [BizTalk アセンブリの依存関係を表示します。](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [BizTalk アセンブリをアプリケーションから削除します。](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)