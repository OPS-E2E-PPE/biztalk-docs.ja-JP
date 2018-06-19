---
title: その他のファイルと BizTalk アプリケーションの設定を削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], deleting settings
- managing [applications], deleting files
- undeploying, settings
- applications, undeploying
- undeploying, files
ms.assetid: b947831a-c988-435c-92ec-45f3fd6967de
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9ad98e0f0fc1e65281a1d8195be4f4a708d004f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255066"
---
# <a name="how-to-remove-other-files-and-settings-for-a-biztalk-application"></a>BizTalk アプリケーションのその他のファイルと設定を削除する方法
このトピックは、アプリケーションをアンインストールするときに、削除できませんを BizTalk アプリケーションのファイルと設定を削除する方法について説明 (で説明した[を BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md))。 たとえば、証明書、COM と COM+ のレジストリ エントリ、および COM ファイルは、アンインストール時にこれらを削除する処理後のスクリプトがアプリケーションに含まれていない場合は、削除されません。  
  
> [!CAUTION]
>  共有アイテムを削除する前に、それらのアイテムが別のアプリケーションで使用されていないことを確認してください。共有されているアイテムを削除すると、そのアイテムを使用するアプリケーションが正常に機能しなくなります。  
  
> [!NOTE]
>  処理後のスクリプトを使用して、この削除を自動化することをお勧めします。 詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。  
  
-   **証明書を削除します。** 証明書ストアから証明書を削除するには、証明書マネージャー (certmgr.exe) コマンド ライン ツールを使用する方法と、証明書スナップインを使用する方法の 2 つの方法があります。 Certmgr.exe は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール前提条件の 1 つである .NET SDK と共にインストールされます。 certmgr.exe は、手動で、または処理後のスクリプトから起動できます。 Certmgr.exe の使用に関する詳細については、次を参照してください。[証明書マネージャー ツール (certmgr.exe)](http://go.microsoft.com/fwlink/?LinkId=56198) 、Microsoft Web サイトです。  
  
     証明書スナップインは、Windows Server 2008 および Windows Vista の両方に含まれています。 証明書を削除するには、スナップインを開いて (詳細については、オペレーティング システムのヘルプの「[証明書] スナップインを起動する」を参照)、証明書を削除します (詳細については、証明書ヘルプの「証明書を削除する」を参照)。  
  
-   **Windows レジストリからアセンブリを削除します。** Windows レジストリから .NET アセンブリおよび BizTalk アセンブリを削除するには、regsvcs または regasm を使用します。これらのツールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール前提条件の 1 つである .NET SDK に含まれています。 リファレンス情報について、次を参照してください。 [.NET サービス インストール ツール (Regsvcs.exe)](http://go.microsoft.com/fwlink/?LinkId=56199)と[アセンブリ登録ツール (Regasm.exe)](http://go.microsoft.com/fwlink/?LinkId=56200) 、Microsoft Web サイトです。  
  
-   **Windows レジストリから COM コンポーネントを削除します。** Windows レジストリから COM コンポーネントを削除するには、regsvr32 を使用します。 詳細については、対象オペレーティング システムのヘルプの「Regsvr32」を参照してください。 このツールは、Windows Server 2008 および Windows Vista Professional の両方に含まれています。  
  
-   **グローバル アセンブリ キャッシュ (GAC) からアセンブリをアンインストールします。** アセンブリは、GAC から自動的にはアンインストールされません。 アセンブリは、手動で、またはスクリプトを使用して GAC からアンインストールできます。 詳細については、次を参照してください。 [GAC からアセンブリをアンインストールする方法](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックで説明されているファイルおよび設定を削除するには、削除する対象に応じて、Windows レジストリ、GAC、または証明書ストアに対する書き込みアクセス許可を持つアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)   
 [BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)