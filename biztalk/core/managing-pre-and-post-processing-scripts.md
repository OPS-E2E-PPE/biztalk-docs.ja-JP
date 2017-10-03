---
title: "前処理および後処理のスクリプトの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18926a0c51e5ab5f65b32373d20b2931ccaa627d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-pre--and-post-processing-scripts"></a>前処理および後処理のスクリプトを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して処理前および処理後のスクリプトを管理する方法について説明します。 BizTalk アプリケーションをインポート、インストール、またはアンインストール (削除) するときに実行するスクリプトを作成して、そのスクリプトをアプリケーションに追加することができます。 スクリプトを追加する際には、処理前のスクリプト (インポートまたはインストールの前、アンインストールの後に実行) か処理後のスクリプト (インポートまたはインストールの後、およびアンインストールの前に実行) かを指定します。  
  
 アプリケーションのエクスポート時にスクリプトを選択する場合、スクリプトはアプリケーションの .msi ファイルに組み込みます。 アプリケーションをインストール、アンインストール、またはインポートする際に、スクリプトが記述に従って自動的に実行されます。 詳細については、作成して、スクリプトを使用して、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順 
  
-   [前または処理後のスクリプトをアプリケーションに追加します。](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [前または処理後のスクリプトの移行先の場所を変更します。](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [前または処理後のスクリプトをアプリケーションから削除します。](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)