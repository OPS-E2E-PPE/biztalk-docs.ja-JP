---
title: TPE を管理するためのユーザー権利 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d88532b21d2a57a2260761ae8b4194ddc0bf5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399918"
---
# <a name="user-rights-for-managing-tpe"></a>TPE を管理するためのユーザー権利
ソリューション開発者、システム管理者、または IT 担当者や運用担当者が、追跡プロファイルを取得したり、アセンブリに関連付けられたデータベースに追跡プロファイルを展開するには、管理権限が必要です。  
  
> [!IMPORTANT]
>  追跡プロファイル エディター (TPE) を使用して、ユーザー ロールを定義したり、ユーザー権限を許可または拒否することはできません。 Microsoft SQL Server では、これらのユーザー ロールおよび関連付けられた権限の定義のみを行えます。  
  
 TPE では、管理者は次の操作を実行できます。  
  
-   BizTalk 管理データベースから、1 つ以上のアセンブリに関連付けられたアクティブな追跡プロファイルを取得します。  
  
-   追跡プロファイルを変更します。  
  
-   新しい追跡プロファイルまたは変更した追跡プロファイルを、BizTalk 管理データベースに適用します。  
  
-   保存済みの追跡プロファイル ファイル (.btt) を変更します。  
  
    > [!NOTE]
    >  追跡プロファイル ファイルは、プロファイルの内容が示される最終的な場所ではありません。 TPE では、主にプロファイルの内容を BizTalk Server から抽出して BAM データベースに公開しますが、プロファイルをファイルに保存できます。 追跡プロファイル ファイルは、ファイルの内容がデータベースに格納されている情報と一致する限り、保存されているプロファイルを編集または更新するために使用できます。 さらに、追跡プロファイル ファイルは、BizTalk Server アプリケーション パッケージ内にパッケージ化できます。 追跡プロファイル ファイルを含むアプリケーション パッケージは、MSI パッケージが特定の BizTalk Server インストールにインポートされると、自動的に BTTDeploy.exe を呼び出して追跡プロファイルを適用します。  
  
> [!IMPORTANT]
>  TPE ワークフローで開発タスクと展開タスクが分離されていると想定した場合、通常、展開の担当者には、.btt ファイルおよび関連付けられたアセンブリ ファイルへの読み取り専用アクセスが必要です。  
  
## <a name="see-also"></a>参照  
 [BAM のワークフロー](../core/bam-workflow.md)   
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)