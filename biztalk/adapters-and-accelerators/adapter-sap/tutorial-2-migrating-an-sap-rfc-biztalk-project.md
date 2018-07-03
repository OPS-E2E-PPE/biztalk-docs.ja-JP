---
title: 'チュートリアル 2: SAP の RFC BizTalk プロジェクトの移行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf741fdbbf996fa54c227cc879c850304413d25f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978987"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a>チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行します。
WCF ベースの Microsoft BizTalk Server に同梱されている SAP アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。  
  
- BizTalk プロジェクトの作成、デザイン時エクスペリエンス。  
  
- メタデータの取得エクスペリエンス。  
  
- スキーマ ファイル名と名前空間。  
  
- データ型のマッピング。  
  
- アダプターを使用して実行できる操作。  
  
- BizTalk Server 管理コンソールで物理ポートの構成。  
  
  これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して、前のバージョン、SAP アダプターの](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)します。  
  
  ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
  このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。  
  
> [!NOTE]
>  説明を簡潔にするため、このチュートリアルでは SAP アダプターの以前のバージョンを vPrev SAP アダプターとして指す場合は。 同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。  
  
## <a name="sample-used-for-the-tutorial"></a>このチュートリアルで使用されるサンプル  
 このチュートリアルは、SAP システムでの RFC を呼び出す vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SAP_RFC_Migration) に基づいています。 サンプルが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。  
  
-   呼び出す vPrev SAP アダプターを使用して、SD_RFC_CUSTOMER_GET RFC を実行する要求メッセージが必要です。 要求メッセージは、RFC vPrev SAP アダプターを使用して生成のスキーマに準拠する必要があります。 このチュートリアルでは提供されたサンプルには、この要求メッセージが含まれています。  
  
-   [厳密な名前のキー ファイルの作成と、ツールの説明](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 RFC を呼び出す vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**します。 これは、簡単なオーケストレーション ポートに送信しますが、SAP を使用して SAP システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信し、別のファイルの場所に保存します。  
  
-   **SAP システムが呼び出す RFC のスキーマ**します。 このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。 RFC に対して生成されたスキーマは、SD_RFC_CUSTOMER_GET__x32003.xsd です。 VPrev SAP アダプターを使用して、このスキーマが生成されます。  
  
-   **要求メッセージ**します。 SD_RFC_CUSTOMER_GET RFC を呼び出す要求メッセージ。 要求メッセージのスキーマは vPrev SAP アダプター、SD_RFC_CUSTOMER_GET RFC のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SAP アダプターによって生成されたスキーマに準拠している要求メッセージを送信できるように、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のスキーマ。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
- WCF ベースを使用して、SD_RFC_CUSTOMER_GET RFC のメタデータを生成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。  
  
- Wcf-custom の SAP の作成、BizTalk Server 管理コンソールのポートの送信-受信します。  
  
- 要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: RFC を呼び出すように vPrev BizTalk プロジェクトを変更する](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成する](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプター チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)