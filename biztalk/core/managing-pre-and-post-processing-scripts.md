---
title: 前処理および後処理のスクリプトの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b39deb7d053ec21677e519852184550d6f3c793d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328043"
---
# <a name="manage-pre--and-post-processing-scripts"></a>前処理および後処理のスクリプトを管理します。

## <a name="overview"></a>概要
このセクションでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、前処理および後処理のスクリプトの管理について説明します。 (削除) を BizTalk アプリケーションのインポート、インストール、またはアンインストール時に実行するスクリプトを作成でき、アプリケーションにスクリプトを追加することができます。 スクリプトを追加するときに、インポート、インストールする前に、アンインストールの後で実行され、処理前のスクリプトまたは実行後、インポートまたはインストールとアンインストールの前に処理後のスクリプトであるかを指定します。  
  
 アプリケーションをエクスポートするときに、スクリプトを選択した場合、スクリプトは、アプリケーションの .msi ファイルに含まれます。 インストール、アンインストール、またはアプリケーションをインポートするときに、スクリプトが自動的に実行、に応じてスクリプトを記述する方法。 詳細については、作成して、スクリプトを使用して、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="next-steps"></a>次のステップ 
  
-   [処理前または処理後のスクリプトをアプリケーションに追加する](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [処理前または処理後のスクリプトの送信先を変更する](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [処理前または処理後のスクリプトをアプリケーションから削除する](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)