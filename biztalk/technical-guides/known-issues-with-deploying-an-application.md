---
title: アプリケーションの配置に関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fa139469ea8718c3d4430235ffb576195e67a7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008235"
---
# <a name="known-issues-with-deploying-an-application"></a>アプリケーションの配置に関する既知の問題
## <a name="deploying-a-biztalk-application"></a>BizTalk アプリケーションの展開  
 **更新されたアプリケーションを展開するには、参照を修正する必要があります。**  
  
 まったく新しいアプリケーションを展開して既存のアプリケーションを置き換える場合は、このアプリケーションと他のアプリケーションとの間の参照をすべて修正する必要があります。  
  
 **Visual Studio を使用してアプリケーションを展開すると、アプリケーションを停止できます。**  
  
> [!NOTE]  
>  運用環境にアプリケーションを配置する Visual Studio を使用しないことをお勧めします。  
  
 関連付けられていないものも含め、アプリケーションを展開するときに、実稼働環境にアプリケーションを配置する Visual Studio を使用して、ホスト インスタンスの再起動オプションが場合プロジェクト プロパティでは、すべてのホスト インスタンスは True に設定が再起動されます。このアプリケーションです。 これにより、ローカル コンピューターのホスト インスタンスで実行されている他のすべてのアプリケーションが停止します。  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>BizTalk アプリケーションにアイテムを追加します。  
 **依存関係を移動できるアイテムの移動します。**  
  
 新しいアプリケーションにアイテムを移動するときの依存関係が存在するその他のアイテムが、新しいアプリケーションに移動した成果物が依存するアイテムを含むアプリケーションへの参照がない限り、移動されます。 また、移動するアイテムに依存しているアイテムも、そのようなアイテムを含むアプリケーションが移動先のアプリケーションを参照している場合を除き、移動先のアプリケーションに移動されます。 アイテムを移動する場合は、同時に移動するその他のアイテムの一覧が表示されます。 アイテムの移動方法の詳細については、次を参照してください。[別のアプリケーションにアイテムを移動する方法](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)。  
  
## <a name="exporting-a-biztalk-application"></a>BizTalk アプリケーションをエクスポートします。  
 **Windows Vista で .msi ファイルをインストールするときに、誤ったエラーが表示されることができます。**  
  
 使用してエクスポートされた .msi パッケージをインストールするときに[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]Windows Vista® で実行されている BizTalk Server で、次の誤ったエラーが表示される、"、インストーラーは、予期しないエラーがこのパッケージのインストールにしました。 このパッケージに問題がある可能性があります。 エラー コード: 2869。" このエラーを修正するには、BizTalk Server を使用してパッケージを最初にインポートし、再度エクスポートしてパッケージをインストールします。  
  
## <a name="importing-a-biztalk-application"></a>BizTalk アプリケーションをインポートします。  
 **パスワードは、アプリケーションに追加されたファイルのバインドから削除されません。**  
  
 セキュリティ上の理由により、パスワードは、アプリケーションのエクスポート中にアプリケーションのバインドから削除されます。 ただし、既にアプリケーションに追加されたバインド ファイルからは削除されません。 アプリケーションをインポートした後、アプリケーションを機能させるためにパスワードを再構成する必要があります。 これは、バインド ファイルを編集するか、管理コンソールを使用して行うことができます。 バインド ファイルの編集の詳細については、次を参照してください。[バインド ファイルのカスタマイズ](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)。 アダプターのセキュリティの構成の詳細については、次を参照してください。[を使用してアダプター](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001)。  
  
 **BizTalk Server ではありませんロールバック スクリプトのインポートまたはインストール**  
  
 インポートに失敗した場合、BizTalk Server によってすべてのインポート操作がロールバックされます。ただし、カスタム スクリプトによって実行される操作は除きます。 これは、インストールにも該当し、操作をアンインストールします。  
  
 **インポート後に、不足しているスキーマを報告されない可能性があります。**  
  
 別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポートにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストールおよび起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。 この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開](../technical-guides/deploying-an-application.md)