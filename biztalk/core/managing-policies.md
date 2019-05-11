---
title: ポリシーの管理 |Microsoft Docs
description: リンクをインポートするには、発行、追加、デプロイ、削除、または BizTalk Server でのポリシーのエクスポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99c3dbc60bde3fdf82dc44a68e34345d3225b92c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380276"
---
# <a name="manage-policies"></a>ポリシーを管理します。

## <a name="overview"></a>概要
このセクションのトピックでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、ポリシーの管理について説明します。 ポリシーは、ビジネス ルールの論理的なグループです。 バック グラウンド ポリシーについては、次を参照してください。[ポリシー](../core/policies.md)します。  
  
## <a name="import-publish-deploy-and-remove-policies"></a>インポート、公開、展開、およびポリシーの削除
 ソリューション開発者が作成および」の説明に従って、ビジネス ルール作成ツールを使用してポリシーの表示[ビジネス ルール作成ツールを使用して作成するビジネス ルール](../core/creating-business-rules-using-the-business-rule-composer.md)します。 開発者と IT 管理者、BizTalk グループおよびアプリケーションでポリシーを展開および管理、このセクションのトピックで説明されている次のタスクを実行できます。  
  
-   **BizTalk グループにポリシーをインポートします。** これを行うときにポリシーは、グループのルール エンジン データベースに追加され、BizTalk Server 管理コンソールに表示されます、\<すべての成果物\>BizTalk グループのノード。 ポリシーを配置、特定のアプリケーションに対して有効にこれはありません。 まず、ポリシーを発行、アプリケーションに追加、およびこのセクションの他のトピックで説明されているように配置し、する必要があります。 ルール エンジン データベースは、すべての BizTalk グループにポリシーを含むデータベースです。  
  
-   **ポリシーを公開します。** BizTalk アプリケーションで使用可能になります。  
  
-   **BizTalk アプリケーションにポリシーを追加します。** これにより、アプリケーションは、ポリシーを使用するが、有効に、ポリシーを配置しません。 展開されているときに、ポリシーを反映します。  
  
    > [!IMPORTANT]
    >  複数のアプリケーションでポリシーを共有するには、ポリシーを格納する独立したアプリケーションを作成した後、そのポリシーを使用する別のアプリケーションからポリシーを格納するアプリケーションへの参照を作成する必要があります。 これは、ポリシーを含むアプリケーションを停止すると、ポリシーが自動的に展開解除され、ポリシーを使用するアプリケーションで機能しなくなるためです。  
  
-   **ポリシーを展開します。** これを行うと、操作に配置します。 (これは、オーケストレーションの開始に似ています) です。展開し、ポリシーを手動で展開解除できます。 さらに、アプリケーションが開始されると、そのポリシーが自動的に展開、およびアプリケーションが停止したら、そのポリシーを自動的に展開されません。  
  
    > [!NOTE]
    >  ポリシーをデプロイするとそれを変更できなくできます。 展開済みのポリシーを変更する場合は、いずれか、展開解除またはビジネス ルール作成ツールを使用して再作成して新しいバージョン番号を指定します。  
  
-   **BizTalk アプリケーションと BizTalk グループからポリシーを削除します。** これは、ポリシーを展開解除され、アプリケーションだけでなく、グループのルール エンジン データベースから削除されます。  
  
-   **ポリシーをエクスポートします。** 使用する別の BizTalk グループに、インポートできます。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="next-steps"></a>次のステップ
  
-   [ポリシーのインポート](../core/how-to-import-a-policy.md)  
  
-   [ポリシーの公開](../core/how-to-publish-a-policy.md)  
  
-   [ポリシーをアプリケーションに追加する](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [ポリシーを展開または展開解除する](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [ポリシーの追跡を構成する](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [アプリケーションおよび BizTalk グループからポリシーを削除する](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [ポリシーをエクスポートする](../core/how-to-export-a-policy.md)