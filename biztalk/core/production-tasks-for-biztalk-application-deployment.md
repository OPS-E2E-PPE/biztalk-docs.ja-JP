---
title: BizTalk アプリケーション展開の実稼働作業 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], assemblies
- applications, deploying
- assemblies, warnings
- deploying [applications], warnings
- deploying [applications], tasks
- assemblies, deploying
- deploying [applications], production
ms.assetid: e77d8921-42ef-4c51-aab2-66c086aad955
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a901028369a0ccde83b4260eacd6dd3784c7b4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396958"
---
# <a name="production-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開の実稼働作業
運用環境に BizTalk アプリケーションの展開に必要な手順を次に示します。  
  
> [!IMPORTANT]
>  実稼働コンピューターの Visual Studio からアセンブリを展開する必要があることはありません。 再展開を有効にするには、Visual Studio 可能性があります展開解除、バインド解除、停止、および同じまたは別のアプリケーション内に存在するアセンブリの参加を解除します。 これは開発環境では必要であり適切なことですが、実稼働環境では予期しない結果や結果や好ましくない結果を引き起こす可能性があります。 さらに、実稼働コンピューターには、Visual Studio からアセンブリを展開しようとしてすべてのユーザーの可能性を回避するためには、実稼働コンピューターに Visual Studio をインストールしないことを勧めします。  
  
> [!IMPORTANT]
>  その他の実行中のアプリケーションを中断しないように、運用環境で他のアプリケーションが依存するアプリケーションを更新するときに注意します。 詳細については、次を参照してください。[アプリケーションの更新に関する重要な考慮事項](../core/important-considerations-for-updating-applications.md)します。  
  
1.  **運用環境に .msi ファイルをコピーします。** 」の説明に従って[BizTalk アプリケーション展開のテスト タスク](../core/testing-tasks-for-biztalk-application-deployment.md)BizTalk アプリケーションは、ステージングが完了し、構成のステージングを行う IT 管理者は、運用環境の準備ができてする .msi ファイルを提供する場合、運用環境のデプロイに使用します。 この .msi ファイルを実稼働コンピューターにコピーし、次に、次の手順で説明した BizTalk アプリケーションを .msi ファイルから BizTalk Server にインポートできます。 また、.msi ファイルを使用するには、アプリケーションを実行するコンピューターにアプリケーションをインストールします。 完全な BizTalk ソリューションを展開する複数の .msi ファイルが表示されるための 1 つまたは複数のアプリケーションで構成できます。  
  
2.  **アプリケーションを .msi ファイルからインポートします。** BizTalk Server 管理コンソールから利用できるインポート ウィザードを使用して、BizTalk Server の現在のインスタンス上のアプリケーションを .msi ファイルの内容をインポートすることができます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 指定したアプリケーションが存在しない場合を作成、.msi ファイルをインポートします。 アプリケーションを表示し、その構成や管理コンソールから内容を変更することができます。 たとえばこれを行うを証明書や Url などのエンドポイントを構成できるだけでなく、運用環境用のバインドを変更する必要があります。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。 バインド ファイルは、運用環境の適切なバインドをアプリケーションに追加された場合、は、インポート処理中に、バインドを適用できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
3.  **インストールし、アプリケーションを起動します。** すべてのコンピューターは、アプリケーションを実行し、管理コンソールで、アプリケーションを起動するアプリケーションをインストールできます。 アプリケーションをインストールするには、.msi ファイルをダブルクリックします。 詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
4.  **バインド ファイルをエクスポートし、(省略可能) のアプリケーションに再度追加します。** 実稼働環境に変更または追加を展開するには、後で、アプリケーションをインポートしやすいように、可能性がありますしたい、アプリケーションのバインドをエクスポートし、アプリケーションに再度追加の運用環境のターゲット環境を指定します。バインドします。 運用環境で BizTalk Server に後でアプリケーションの .msi ファイルをインポートする場合は、これらのバインドが適用されることを指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
5.  **(省略可能) 新しい .msi ファイルにアプリケーションをエクスポートします。** 構成の変更、または、アプリケーションに追加し (たとえば他の BizTalk グループにアプリケーションをデプロイするなど)、.msi ファイルに反映される変更を反映する場合」の説明に従って、新しい .msi ファイルをエクスポートできます[エクスポートする方法、BizTalk アプリケーション](../core/how-to-export-a-biztalk-application.md)します。  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開作業](../core/application-deployment-tasks.md)