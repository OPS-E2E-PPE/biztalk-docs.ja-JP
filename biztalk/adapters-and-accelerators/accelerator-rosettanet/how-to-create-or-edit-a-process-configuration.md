---
title: "作成またはプロセス構成を編集する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- authorization properties
- non-repudiation, properties
- creating, process configuration
- modifying, process configuration
ms.assetid: ef6160f1-f2f0-42ff-a516-7818c9d79d26
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4c9c9be5e9f3361683e495febbd98a05156399d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-or-edit-a-process-configuration"></a>作成またはプロセス構成を編集する方法
ここでは、プロセス構成の作成方法または編集方法について説明します。  
  
 次の表に、プロセス構成の設定をタブごとに整理して示します。表の後に、プロセス構成を作成および編集する手順を示します。  
  
 承認プロパティと否認不可プロパティは独立しています。 これらのプロパティを設定する方法の詳細については、次を参照してください。[承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)です。  
  
|タブ|設定|使用方法|  
|---------|-------------|-----------|  
|**全般**|**コードを表示します。**|PIP (Partner Interface Process) の表示コード。 RosettaNet PIP 指定またはカスタム スキーマの名前のいずれかに対応します。 たとえば "STD_3A2_R02.00.00A" のように、プロセス コードとバージョンを名前に含めるなど、標準の名前付け規則を使用することをお勧めします。 これにより、同じ PIP の異なるバージョンを容易に管理できます。<br /><br /> 必須フィールド。|  
|**全般**|**プロセス コード**|3 桁の PIP コード。 たとえば "3A2" など。<br /><br /> 必須フィールド。|  
|**全般**|**バージョン**|PIP のバージョン。 たとえば "V02.02" または "R02.00.00A" など。<br /><br /> 必須フィールド。|  
|**全般**|**プロセス名**|PIP の名前。 たとえば "Price and Availability Request Action" など<br /><br /> 必須フィールド。|  
|**全般**|**Description**|PIP に準拠するメッセージの説明。|  
|**全般**|**Standard**|標準の種類。<br /><br /> 設定可能値 : RosettaNet (既定値) または CIDX|  
|**全般**<br /><br /> ("RosettaNet 以外のコンテンツ" 領域)|**標準的なメッセージ**|RosettaNet 以外のコンテンツの場合は、RosettaNet 以外の標準の名前。 この設定は、RosettaNet PIP は使用していないが、カスタム スキーマが定義済みの場合に使用します。 この設定は RNIF 2.0 でのみ使用し、RNIF 1.1 と CIDX には使用しないでください。|  
|**全般**<br /><br /> ("RosettaNet 以外のコンテンツ" 領域)|**標準のバージョン**|RosettaNet 以外のコンテンツの場合は、RosettaNet 以外の標準のバージョン。 この設定は、RosettaNet PIP は使用していないが、カスタム スキーマが定義済みの場合に使用します。 この設定は RNIF 2.0 でのみ使用し、RNIF 1.1 と CIDX には使用しないでください。|  
|**全般**<br /><br /> ("RosettaNet 以外のコンテンツ" 領域)|**ペイロードのバインド ID**|RosettaNet 以外のコンテンツの場合は、ペイロード コンテンツの ID 番号。 この設定は、RosettaNet PIP は使用していないが、カスタム スキーマが定義済みの場合に使用します。 カスタム PIP を実装しているパーティでは、この値を定義する必要があります。 この設定は RNIF 2.0 でのみ使用し、RNIF 1.1 と CIDX には使用しないでください。|  
|**アクティビティ**<br /><br /> ("受信の確認" 領域)|**否認不可が必要**|否認不可を目的として、(受信確認メッセージにメッセージのダイジェストを含む) シグナル メッセージに署名する必要があるかどうか、および受信側のパーティがそのメッセージを元の形式で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースの MessageStorageIn テーブルまたは MessageStorageOut テーブルに格納する必要があるかどうかを指定します。 指定された期間に、受信側パーティがシグナルを格納する必要があります、**配信元の否認**パートナー構成においてプロパティです。<br /><br /> 設定可能値: `True` (既定値) または `False`<br /><br /> `False` の場合、シグナル メッセージが否認不可目的で格納されることはありません。 シグナル メッセージへの署名の有無は問いません。<br /><br /> `True` の場合、受信シグナル メッセージは元の形式で MessageStorageIn テーブルに格納されます。 送信シグナル メッセージは、元の形式で MessageStorageOut テーブルに格納されます。 シグナル メッセージへの署名は必須です。<br /><br /> 詳細については、次を参照してください。[承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)です。|  
|**アクティビティ**<br /><br /> ("受信の確認" 領域)|**受信確認の時間 (秒)**|開始側が受信確認を受信するまでの秒数。 イニシエーターが再試行を超えていない場合に再試行イニシエーターを受け取らない場合、この時点で、**再試行**カウント (で、**動作**このタブのセクション)。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]メジャー、**受信確認時間**値の時間から、発信側がアクション メッセージを正常に送信します。 値は Delivery Header に含まれます。 値は 0 より大きいか小さいにすることはできません、**実行までの時間**同じページに設定されている値。<br /><br /> この設定は、RNIF 1.1 および 2.01 の処理で返されたシグナル メッセージ (アプリケーション確認) に対して使用します。 また、RNIF 1.1 の処理で返された受信確認にも使用します。<br /><br /> 既定値は 7,200 秒 (2 時間) です。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**認証の必要性します。**|すべての受信アクションまたはシグナル メッセージに署名が必要かどうかを判断します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]個人またはロールは、アクティビティを実行する権限がない場合は、ビジネス ドキュメントを受け入れません。<br /><br /> 設定可能値: `True` (既定値) または `False`<br /><br /> `False` の場合、送信アクション メッセージと送信シグナル メッセージは署名されません。 受信アクション メッセージと受信シグナル メッセージには署名される場合があります。 署名がない場合は、Delivery Header を使用してパートナーが承認されます。<br /><br /> `True` の場合は、着信メッセージに署名が必要です。 送信メッセージに署名される場合もあります。 場合にのみ、送信メッセージは署名されて**発信元とコンテンツの否認**に設定されている`True`です。<br /><br /> 詳細については、次を参照してください。[承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)です。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**永続的な機密性の必要性**|暗号化の必要があるかどうかを指定します。<br /><br /> 使用可能な値: **None** (既定) は、暗号化が不要であることを示します。 **ペイロード**示す service content と添付ファイルの暗号化が必要です。 **ペイロード コンテナー**暗号化することを示しますの service content、添付ファイル、およびサービスのヘッダーが必要です。<br /><br /> RNIF 2.0 の場合、Preamble Header および Delivery Header は暗号化されません。 RNIF 1.1 の場合、メッセージ部分は暗号化されません。 署名されるだけです。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**必要な保護されたトランスポートします。**|HTTPS トランスポートの必要があるかどうかを指定します。<br /><br /> 設定可能値: `True` (既定値) または `False`|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**シングル アクションします。**|メッセージがシングル アクションか、またはダブル アクションかを指定します。<br /><br /> 設定可能値: `True` (既定値) または `False`<br /><br /> シングル アクション メッセージは "情報の配布" または "通知" です。 ダブル アクション メッセージには "取り引き"、"要求/確認"、"要求/応答"、"クエリ/応答" があります。<br /><br /> 標準の CIDX 場合、**シングル アクション**する必要があります**True**です。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**同期型**|取引先でのアクション メッセージの交換を同期的に行うか、非同期的に行うかを指定します。<br /><br /> 使用可能な値:`True`または`False`(既定)<br /><br /> RNIF 1.1 では使用しません。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**発信元とコンテンツの否認**|否認不可を目的として、受信側のパーティがアクション メッセージに署名し、BTARNArchive データベースの MessageStorageIn テーブルまたは MessageStorageOut テーブルに元の形式で格納する必要があるかどうかを指定します。 指定された期間に、受信側パーティがアクション メッセージを格納する必要があります、**配信元の否認**否認不可用のパートナー構成内のプロパティです。 必要に応じて、アクション メッセージに署名します。<br /><br /> 設定可能値: `True` (既定値) または `False`<br /><br /> `False` の場合、アクション メッセージが否認不可を目的で格納されることはありません。 アクション メッセージへの署名の有無は問いません。<br /><br /> `True` の場合、受信アクション メッセージは MessageStorageIn テーブルに元の形式で格納されます。 送信アクション メッセージは、MessageStorageOut テーブルに元の形式で格納されます。 アクション メッセージへの署名は必須です。<br /><br /> 詳細については、次を参照してください。[承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)です。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**再試行の回数**|トランスポートまたは処理が失敗した場合にプロセスがアクティビティを再試行する回数。 再試行回数が 3 の場合、プロセスはそのアクティビティを 4 回試行します。<br /><br /> 既定値は、3 です。<br /><br /> 通信は、同期処理し、場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]再試行は、同期トランザクションには適用されないために、このフィールドを使用しません。|  
|**アクティビティ**<br /><br /> ("動作" 領域)|**実行する時間**|プロセスがアクティビティを完了するまでの期間 (秒)。 この期間が開始されるのは、開始側が最初のドキュメントを送信した時点です。 開始側 (応答側ではない) は、この期間内にアクティビティを完了させる必要があります。 この値は Delivery Header にあります。<br /><br /> 既定値は 86,400 秒 (24 時間) です。<br /><br /> **実行までの時間**値より大きくなければなりません、**受信確認時間**で設定されている値、**受信の**同じページのセクションでします。|  
|**アクティビティ**<br /><br /> ("全般" 領域)|**型**|アクティビティの種類を指定します。<br /><br /> 使用可能な値:**ビジネス トランザクション**、**情報の配布**(既定)、**通知**、**クエリ/応答**、 **要求/確認**、または**要求/応答**|  
|**イニシエーター**<br /><br /> ("ビジネス ドキュメント" 領域)|**Description**|開始側アクションのビジネス ドキュメントの説明。|  
|**イニシエーター**<br /><br /> ("ビジネス ドキュメント" 領域)|**名前**|開始側アクションのビジネス ドキュメントの名前。 たとえば "Price and Availability Request" (価格とアベイラビリティの要求) など。|  
|**イニシエーター**<br /><br /> ("ビジネス ドキュメント" 領域)|**バージョン**|ビジネス ドキュメントのバージョン。 たとえば "V02_02_00" または "R02.00.00A" など。<br /><br /> このバージョン番号は、RosettaNet 組織から PIP 仕様 .doc ファイルおよび PIP DTD と共にダウンロードした、RosettaNet XML メッセージ ガイドライン .htm ファイルの最初に記載されています。|  
|**イニシエーター**<br /><br /> ("全般" 領域)|**操作**|開始側アクションの説明。 たとえば "Synchronous Test Query Action" (同期のテスト照会アクション) など。|  
|**イニシエーター**<br /><br /> ("全般" 領域)|**ロール**|開始側のロール。 たとえば "Buyer" (購入側) または "Payer" (支払側) など。<br /><br /> 既定値は "Initiator" (開始側) です。|  
|**イニシエーター**<br /><br /> ("全般" 領域)|**ロールの説明**|開始側のロールの説明。 たとえば "The party issuing the payment" (支払いを発行しているパーティ) など。|  
|**イニシエーター**<br /><br /> ("全般" 領域)|**ロールの種類**|開始側のロールの種類。<br /><br /> 使用可能な値:**組織**、**従業員**、または**機能**(既定)|  
|**イニシエーター**<br /><br /> ("全般" 領域)|**サービス**|開始側のサービス。 たとえば "Buyer Service" (購入側サービス) または "Payer Service" (支払側サービス) など。|  
|**イニシエーター**<br /><br /> ("全般" 領域)|**サービスの分類**|開始側サービスの種類。 たとえば "Business Service" (ビジネス サービス) など。|  
|**応答側**<br /><br /> ("ビジネス ドキュメント" 領域)|**Description**|応答側アクションのビジネス ドキュメントの説明。 たとえば "Formally confirms the status of line items in a purchase order" (発注書の品目の状態を正式に確認する) など。|  
|**応答側**<br /><br /> ("ビジネス ドキュメント" 領域)|**名前**|応答側アクションのビジネス ドキュメントの名前。 たとえば "Purchase Order Confirmation" (発注確認) など。|  
|**応答側**<br /><br /> ("ビジネス ドキュメント" 領域)|**バージョン**|ビジネス ドキュメントのバージョン。 たとえば "V02.02.00" または "R02.00.00A" など。 このバージョン番号は、RosettaNet 組織から PIP 仕様 .doc ファイルおよび PIP DTD と共にダウンロードした、RosettaNet XML メッセージ ガイドライン .htm ファイルの最初に記載されています。|  
|**応答側**<br /><br /> ("全般" 領域)|**操作**|応答側アクションの説明。 たとえば "Purchase Order Confirmation Action" (発注確認アクション) など。|  
|**応答側**<br /><br /> ("全般" 領域)|**ロール**|応答側のロール。 たとえば "販売者" など。<br /><br /> 既定値は "Responder" (応答側) です。|  
|**応答側**<br /><br /> ("全般" 領域)|**ロールの説明**|応答側のロールの説明。 たとえば "The party receiving payment" (支払いを受けるパーティ) など。|  
|**応答側**<br /><br /> ("全般" 領域)|**ロールの種類**|応答側のロールの種類。<br /><br /> 使用可能な値:**組織**(既定)、**従業員**、または**機能**|  
|**応答側**<br /><br /> ("全般" 領域)|**サービス**|応答側のサービス。 たとえば "Seller Service" (販売者サービス) など。|  
|**応答側**<br /><br /> ("全般" 領域)|**サービスの分類**|応答側サービスの種類。 たとえば "Business Service" (ビジネス サービス) など。|  
  
### <a name="to-implement-a-new-process-configuration"></a>新しい構成を実装するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3.  右クリック**プロセス構成設定**、 をポイント**新規**、クリックして**プロセス構成**です。  
  
4.  新しいプロセス構成のプロパティ ダイアログ ボックスで、**全般**、**アクティビティ**、**イニシエーター**、および**レスポンダー**タブで、「上記で一覧した設定の値は、テーブル、およびをクリックして**OK**です。  
  
### <a name="to-edit-a-process-configuration"></a>プロセス構成を編集するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3.  をクリックして**プロセス構成の設定**です。  
  
4.  プロセス構成を編集して、をクリックするを右クリックして**プロパティ**です。  
  
5.  *\<プロセス構成 >*プロパティ ダイアログ ボックスで、**全般**と**連絡先のプロパティ**タブで、必要に応じて設定を変更します。 これらの設定の詳細については、上の表を参照してください。  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [PIP 仕様を使用して、プロセス構成を作成するには](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)   
 [承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)   
 [設定を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)   
 [BTARN 構成の管理](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)