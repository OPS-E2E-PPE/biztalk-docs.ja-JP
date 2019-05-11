---
title: アプリケーションの展開と管理ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de85b52b-7eb7-4cf1-b8b4-41f7488b4d2f
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d0d1881eeb8d5480afea46747ecc17e425de38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359082"
---
# <a name="application-deployment-and-management-tools"></a>アプリケーションの展開および管理のツール

## <a name="overview"></a>概要
このトピックでは、BizTalk アプリケーションの展開および管理に使用できるツールについて簡単に説明し、各ツールで実行できる操作についての概要を示します。 このトピックの最後にある表は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールと BTSTask を使用して実行できるタスクをまとめたものです。  

- **BizTalk Server 管理コンソール。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Microsoft 管理コンソール (MMC)、主要な管理ツールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 この管理コンソールでは、BizTalk アプリケーションのすべての展開操作および管理操作を実行するためのグラフィカル ユーザー インターフェイスを提供します。 たとえば、管理コンソールから、アプリケーションのアイテムを追加および削除したり、その他の変更をアプリケーションに加えたりするだけでなく、インポート ウィザード、インストール ウィザード、エクスポート ウィザードなどを起動することもできます。  

   次の説明に従って、MSI ファイルのエクスポート ウィザードまたは BTSTask を使用して、BizTalk アプリケーションの BizTalk .msi ファイルも生成します。 その後、.msi ファイルからコンピューターにアプリケーションをインストールしたり、.msi ファイルからアプリケーションを別の BizTalk グループにインポートしたりすることができます。 管理コンソールの詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。  

- **BTSTask コマンド ライン ツールです。** BTSTask を使用すると、コマンド ラインから多くのアプリケーション管理タスクを実行できます。 詳細については、BTSTask を使用して、次を参照してください。 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)します。  

- **スクリプトとプログラミング Api**します。 Microsoft Windows Management Instrumentation (WMI) を使用して、多くのアプリケーション管理タスクを自動化するスクリプトを作成および実行することができます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  

- **Visual Studio。** 開発者で BizTalk アセンブリを作成できます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]展開コマンドを使用して BizTalk アプリケーションに自動的に展開するとします。 詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  

   .  

  > [!IMPORTANT]
  >  実稼働コンピューターで実行中の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からアセンブリを展開することはできません。 このような操作によって、アプリケーションの実行が中断される可能性があります。 詳細については、次を参照してください。 [BizTalk アプリケーションの展開のベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)します。  

## <a name="tool-by-the-task"></a>タスクによってツール  
 次の表は、管理コンソールと BTSTask を使用して実行できるタスクをまとめたものです。  


|                                        タスク                                         |                                                                                       ツール                                                                                       |
|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           アプリケーションの .msi ファイルのエクスポート                           |           -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール <br/>– MSI ファイルのウィザードをエクスポートします。<br />-BTSTask           |
|                           アプリケーションの .msi ファイルのインポート                           |             -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール <br/>– MSI のインポート ウィザード<br />-BTSTask              |
|                           アプリケーションの作成または削除                           |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール<br />-BTSTask                          |
|                               アプリケーションをインストールします。                                | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール <br/>– インストール ウィザード (またはアプリケーションの .msi ファイルをダブルクリックします) |
|                              アプリケーションをアンインストールします。                               |                                                              BTSTask (またはコントロール パネルの [プログラムの追加と削除] の使用)                                                               |
|       アプリケーションへのアイテムの追加またはアプリケーションからのアイテムの削除       |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール<br />-BTSTask                          |
|                    バインドおよびバインド ファイルのインポートおよびエクスポート                     |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール<br />-BTSTask                          |
|                             ポリシーのインポートおよびエクスポート                              |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール<br />-BTSTask                          |
|                            アプリケーションの開始と停止                            |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール                                     |
| 成果物の状態を変更します開始、停止、有効にする、無効にする、参加、および参加解除。 |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール                                     |
|                              アイテムのプロパティの編集                               |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール                                     |
|       送信ポート、送信ポート グループ、受信場所、または受信ポートの作成        |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール                                     |

## <a name="see-also"></a>参照  
[管理およびパフォーマンス ツール](../core/administration-tools.md)  
 [BizTalk アプリケーションの展開と管理について](../core/understanding-biztalk-application-deployment-and-management.md)