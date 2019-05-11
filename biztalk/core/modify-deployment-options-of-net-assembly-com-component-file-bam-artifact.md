---
title: .NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a516857d6f790dfd1d5f4c7ad51c34144913785b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324581"
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a>.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、次のリソース アイテムの展開オプションを変更する方法について説明します。  
  
- .NET アセンブリ  
  
- COM コンポーネント  
  
- アドホック ファイル  
  
- BAM アイテム  
  
  アプリケーションがローカル コンピューターにインストールされているとき、成果物のファイルにコピーされます変換先の場所を変更する配置プロパティを変更したい場合があります。 パスを指定しない場合、ファイルはインストールでローカル コンピューターにコピーされません。  
  
  さらに、.NET アセンブリの次のオプションを変更する可能性があります。  
  
- **グローバル アセンブリ キャッシュへの追加に (gacutil) のリソースを追加します。** このオプションを選択すると、アセンブリでアセンブリがアプリケーションに追加されたときにローカル コンピューターの追加をグローバル アセンブリ キャッシュ (GAC) されます。 さらに、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。 このオプションのチェック ボックスをオフにするとは削除されません、アセンブリを GAC から現在存在する場合があります。  
  
- **MSI ファイルのインポート (gacutil) のグローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートする場合に、このオプションを選択すると、インポート プロセスの一環として、ローカル コンピューターの GAC にアセンブリがインストールされています。  
  
- **MSI ファイル インストール (gacutil)、グローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、アセンブリはインストール プロセスの一環として、ローカル コンピューターの GAC にインストールされています。  
  
- **COM コンポーネント (regasm) に表示されるようにします。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、マネージ COM アセンブリは、インストール プロセスの一環として、ローカル コンピューター上の Windows レジストリに追加されます。 このオプションを指定する場合は、先にもファイルの場所を指定する必要があります。  
  
- **コンポーネント (regsvcs) を登録サービスを提供します。** アプリケーションが .msi ファイルにエクスポートし、アプリケーションが .msi ファイルからコンピューターにインストールされている場合、このオプションを選択すると、マネージ COM + アセンブリがインストール プロセスの一環として、ローカル コンピューター上の Windows レジストリに追加されます。 このオプションを指定する場合は、先にもファイルの場所を指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 さらに、すぐに、GAC にアセンブリを追加するオプションを選択すると、自分のアカウントに、ローカル管理者グループのメンバーがあるも必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a>リソース アイテムの展開プロパティを変更するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開オプションを変更する対象のアイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。  
  
3. をクリックして、**リソース**フォルダーは、アイテムを右クリックし、順にクリックします**変更**します。  
  
4. **オプション** タブで、必要に応じて、展開オプションを変更し、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)