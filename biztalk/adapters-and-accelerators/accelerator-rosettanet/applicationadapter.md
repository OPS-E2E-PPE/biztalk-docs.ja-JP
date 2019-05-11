---
title: ApplicationAdapter |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9b876b-cd37-4e24-a476-186adc155ac0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a738003a3afb9f34e4546d1a1865e99376e8fba6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284911"
---
# <a name="applicationadapter"></a>ApplicationAdapter
ApplicationAdapter サンプルでは、パブリックおよびプライベート プロセス (応答側または発信側) から通知を送信すると、メッセージが表示されます。 必要な追加機能では、サンプルをカスタマイズできます。  
  
 ApplicationAdapter サンプルは、実装する方法を示します、`IApplicationAdapter`へのインターフェイス、`ApplicationAdapter1`クラス。 このクラスには、2 つのメソッドが含まれています。`BeginNotify`と`Notify`します。 各クラスのパラメーターは、メッセージ カテゴリ、送信元パーティ名、送信先パーティ名、プロセス PIP (Partner Interface) コード、PIP インスタンス ID、および PIP バージョン。  
  
 アセンブリ名とクラス名を入力して、アグリーメントの ApplicationAdapter を設定する、**全般**Microsoft® でアグリーメントのタブ[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソール。 アプリケーション アダプタの .dll ファイルは、BizTalk ホスト サービスと同じ資格情報で実行されます。  
  
 ApplicationAdapter サンプルまたは ApplicationAdapter サンプルが依存している任意の外部の環境変数を変更する場合をホストする BizTalk ホスト サービスを再起動、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パブリック プロセス。  
  
 ApplicationAdapter サンプル コードは\<*ドライブ*\>: \Program Files\ BizTalk\<バージョン\>Accelerator RosettaNet\SDK\ApplicationAdapterfor\\.  
  
## <a name="demonstrates"></a>使用例  
 ApplicationAdapter サンプルでは、パブリック プロセスがメッセージを受信する応答側プライベート プロセスに通知する方法を示します。 通知は、メッセージ カテゴリ、送信元のパーティ名、送信先パーティ名、PIP コード、PIP バージョン、および PIP インスタンス id。 ことを示します。 アクションまたは応答メッセージには、この通知を送信できます。  
  
 `BeginNotify`と`Notify`メソッドは次のように動作します。  
  
1.  応答側パブリック プロセスは、メッセージを受け取ります。  
  
    > [!NOTE]
    >  パブリック開始側が応答側から応答メッセージを受信するシナリオは、次の手順も。  
  
2.  応答側パブリックが呼び出しを処理、受信パイプラインとパブリック プロセスと、検証アダプターによる検証が該当する場合の指定が、成功した場合、`BeginNotify`メソッドで、`ApplicationAdapter`クラス。 このメソッドは、パブリック プロセスが、新しいメッセージを受信し、メッセージ ボックス データベースにメッセージを保存、応答側プライベート プロセスを通知します。  
  
3.  応答側パブリック プロセスは、発信側にシグナル メッセージを送信します。  
  
4.  応答側パブリック プロセスは、メッセージの service content を応答側プライベート プロセスに送信します。  
  
5.  応答側プライベート プロセスは、BTARNDATA データベースの MessagesToLOB テーブルにメッセージを配置します。  
  
6.  応答側プライベート プロセスの呼び出し、`Notify`メソッドで、 `ApplicationAdapter` End Notify メッセージを応答側パブリック プロセスに送信するクラス。 応答側パブリック プロセスには、プロセスが正常に完了する End Notify メッセージを受信する必要があります。 それ以外の場合、メッセージは中断されます。  
  
> [!NOTE]
>  使用することができます、`Notify`基幹業務 (LOB) アプリケーションにメッセージが MessagesToLOB テーブルで待機していることを通知するメッセージ。 すぐに、システム、LOB アプリケーションの警告、LOB アプリケーションは、そのテーブルからメッセージを取得することができます。  
  
## <a name="to-implement-this-sample"></a>このサンプルを実装するには  
 ApplicationAdapter サンプルを実装するには、アグリーメントをアプリケーション アダプターを追加する必要があります。  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a>アプリケーション アダプターをアグリーメントに追加するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、microsoft **BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。  
  
2. [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリック**契約**します。  
  
3. アプリケーション アダプターを追加するアグリーメントをダブルクリックします。  
  
4. **アプリケーション アダプター**ボックスで、省略記号ボタンをクリックします (**.**) ボタンの右側に**アセンブリ名**、アプリケーション アダプターのアセンブリを格納している場所に移動、適切な .dll ファイルを選択およびクリックして**オープン**します。  
  
5. 下矢印をクリックして**クラス名**アプリケーション アダプター クラスを選択し、クリックして**OK**。  
  
## <a name="see-also"></a>参照  
 [アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)